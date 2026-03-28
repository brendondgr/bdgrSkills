---
name: LangGraph Structure Standard
description: File structure and organization standards for LangGraph implementations.
---

# LangGraph Structure

A clean LangGraph repository usually works best when you separate **graph wiring**, **business logic**, **state/schema**, and **infrastructure concerns** instead of putting everything into one large `agent.py`. LangChain’s own LangGraph application structure recommends a project with app code in one package plus `langgraph.json`, dependency files, and optional environment config, which is a good baseline to build on.

## Recommended layout

LangChain’s docs show a typical LangGraph app with a dedicated package for project code, utility modules for tools, nodes, and state, plus root-level deployment files such as `langgraph.json`, `requirements.txt` or `pyproject.toml`, and `.env`.  Building on that, a maintainable repo often looks like this:

```text
my-langgraph-app/
├── README.md
├── pyproject.toml
├── langgraph.json
├── .env.example
├── .gitignore
├── tests/
│   ├── unit/
│   ├── integration/
│   └── evals/
├── docs/
│   ├── architecture.md
│   ├── state-model.md
│   └── runbooks/
├── scripts/
│   ├── dev.py
│   └── seed_data.py
├── utils/
│   └── my_agent/
│       ├── __init__.py
│       ├── main.py                 # app entrypoint / graph export
│       ├── config.py               # settings, env loading
│       ├── state/
│       │   ├── __init__.py
│       │   ├── schemas.py          # TypedDict / Pydantic models
│       │   └── reducers.py
│       ├── graphs/
│       │   ├── __init__.py
│       │   ├── assistant_graph.py
│       │   └── retrieval_graph.py
│       ├── nodes/
│       │   ├── __init__.py
│       │   ├── planner.py
│       │   ├── responder.py
│       │   └── router.py
│       ├── tools/
│       │   ├── __init__.py
│       │   ├── search.py
│       │   └── crm.py
│       ├── services/
│       │   ├── llm.py
│       │   ├── vectorstore.py
│       │   └── memory.py
│       ├── prompts/
│       │   ├── system.py
│       │   └── templates/
│       └── observability/
│           ├── logging.py
│           └── tracing.py
└── notebooks/
    └── experiments.ipynb
```

## Folder roles

Keep `graphs/` focused only on assembling nodes, edges, conditional routing, and compilation, since LangGraph itself centers on defining graphs and compiling them into deployable applications.  Put actual node behavior in `nodes/`, tool wrappers in `tools/`, and shared external integrations like model clients or vector stores in `services/`, so each layer has a single reason to change.

Keep state definitions isolated in `state/`, because state is one of the core concepts in LangGraph graph design and tends to become the hidden source of complexity if it is spread across files.  Put prompts in their own `prompts/` directory instead of embedding them inside nodes, which makes prompt iteration safer and easier to review.

## Practical rules

A few conventions keep the repo easy to understand:

- One graph per file when possible; if a workflow grows large, split subgraphs into separate files and compose them from a top-level graph module. LangGraph supports one or more graphs configured via `langgraph.json`, so this scales cleanly.
- One node function per clear responsibility, for example `classify_intent`, `retrieve_context`, `draft_answer`, rather than a single `run_agent` node that does everything. This matches LangGraph’s node-and-edge model more naturally.
- Keep `main.py` or a single export module very thin; it should mostly expose the compiled graph referenced by `langgraph.json`. The docs describe the config file as the place where graph paths are registered for deployment.
- Put experiments in `notebooks/` or `experiments/`, not inside `utils/`, because the official examples repository contains many distinct example applications and patterns, which is useful for learning but can become noisy in a production repo if mixed with core app code.

## What to avoid

Avoid organizing by technical sprawl like `utils.py`, `helpers.py`, and `misc.py`, because those files become dumping grounds and make graph behavior harder to trace. The official example and docs structure is more explicit, naming modules around tools, nodes, state, and agent construction.

Also avoid mixing deployment files, prompt text, graph compilation, and provider-specific setup in one file. LangGraph is intentionally a low-level orchestration layer for long-running, stateful workflows, so cleanliness comes from making orchestration separate from implementation details.

## Minimal baseline

If you want the simplest version that still stays clean, start with this:

```text
utils/my_agent/
├── main.py
├── state.py
├── nodes.py
├── tools.py
└── prompts.py
```

That mirrors the structure shown in LangChain’s docs and is enough for a small project. As soon as you have more than one graph, multiple external integrations, or more than 5 to 7 nodes, split into the larger package structure above so the repository remains readable.

A good rule of thumb is: if a new contributor cannot answer “where is the state defined, where is the graph wired, and where is the tool logic implemented?” in under a minute, the repo structure needs tightening.
