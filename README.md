# Agent Templates Hub

A tiered catalog of production-ready agent and backend templates. Every template family
ships in multiple tiers — **POC → Intermediate → Advanced** — so you can start
prototyping in minutes and grow into a real deployment without switching frameworks
or rewriting from scratch.

If a repo saves you time, a ⭐ helps others find it.

---

## How this catalog works

Each **family** below solves one kind of problem (orchestration, document Q&A, backend
scaffolding). Within a family, tiers share the same core logic and API shape — moving
up a tier adds auth, persistence, multi-tenancy, or SSO, not a different mental model.
Pick the lowest tier that meets your actual requirements; each repo's README explains
exactly when to move up.

---

## 🧭 Multi-Agent Orchestrator Templates

Dynamic Supervisor routing across specialist agents — for workflows where the next
step genuinely depends on what previous steps found, not a fixed pipeline.

| Tier                   | Framework   | Use it when...                                                                     | Repo                                                                                                                               |
| ---------------------- | ----------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| POC                    | LangGraph   | Prototyping the agent flow itself. In-memory state, minutes to first run.          | [agent-template-orchestrator-poc](https://github.com/MettaSurendhar/agent-template-orchestrator-poc)                               |
| Intermediate           | LangGraph   | Real users, runs need to survive a restart, want auth + audit.                     | [agent-template-orchestrator-intermediate](https://github.com/MettaSurendhar/agent-template-orchestrator-intermediate)             |
| Advanced — LangGraph   | LangGraph   | Real organization: Postgres state at scale, SSO, per-team isolation, review queue. | [agent-template-orchestrator-advanced-langgraph](https://github.com/MettaSurendhar/agent-template-orchestrator-advanced-langgraph) |
| Advanced — AWS Strands | AWS Strands | Same production feature set as above, built on AWS Strands Agents SDK instead.     | [agent-template-orchestrator-advanced-strands](https://github.com/MettaSurendhar/agent-template-orchestrator-advanced-strands)     |

<!-- TABLE:orchestrator:end -->

## 📄 Document Intelligence (RAG) Agent Templates

Citation-grounded, team-scoped document Q&A agents — retrieval strictly bound to your
own documents, no silent hallucination.

| Tier         | Use it when...                                                                              | Repo                                                                                                                       |
| ------------ | ------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| POC          | Prototyping or demoing. Single-user, no auth, ChromaDB, minutes to first answer.            | [agent-template-document-intel-poc](https://github.com/MettaSurendhar/agent-template-document-intel-poc)                   |
| Intermediate | Real users needing isolation, FAISS vs. Chroma comparison, an audit trail.                  | [agent-template-document-intel-intermediate](https://github.com/MettaSurendhar/agent-template-document-intel-intermediate) |
| Advanced     | Real team/org: multi-team isolation, SSO, compliance-grade audit, AWS Bedrock + OpenSearch. | [agent-template-document-intel-advanced](https://github.com/MettaSurendhar/agent-template-document-intel-advanced)         |

<!-- TABLE:document-intel:end -->

## 🧱 Node/Express Backend Templates

Plain backend scaffolding — no agent logic, just a solid starting point for an API server.

| Template                    | Use it when...                                                                        | Repo                                                                                                                               |
| --------------------------- | ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Node/Express — Beginner     | You want the simplest possible Express starting point.                                | [node-express-backend-template-for-beginner](https://github.com/MettaSurendhar/node-express-backend-template-for-beginner)         |
| Node/Express — Intermediate | You want structure: routing, middleware, error handling conventions already in place. | [node-express-backend-template-for-intermediate](https://github.com/MettaSurendhar/node-express-backend-template-for-intermediate) |

<!-- TABLE:node-express:end -->

## 🔧 Other Templates & Reference Projects

| Repo                                                                                 | What it is                                                 |
| ------------------------------------------------------------------------------------ | ---------------------------------------------------------- |
| [express-api-boilerplate](https://github.com/MettaSurendhar/express-api-boilerplate) | General-purpose Express API boilerplate.                   |
| [Met-Social-Media-API](https://github.com/MettaSurendhar/Met-Social-Media-API)       | Reference implementation of a social-media style REST API. |

<!-- TABLE:other:end -->
<!-- FAMILIES:end -->

---

## Which family do I want?

- **Building something that needs to decide its own next step** (classify → analyze →
  validate → recommend, order not fixed) → **Orchestrator** family.
- **Building a Q&A agent grounded in a specific set of documents** (HR policy, contracts,
  specs) → **Document Intel** family.
- **Just need a backend to build on, no agent logic** → **Node/Express** templates.

Every family follows the same tier logic: start at POC to validate the idea cheaply,
move to Intermediate once you have real users, move to Advanced once you're deploying
for a real team/org (multi-tenancy, SSO, compliance-grade audit).

## Contributing

Found a template that fits this catalog (yours or someone else's), or want to propose
a new tier/family? See [CONTRIBUTING.md](./CONTRIBUTING.md).

## License

MIT — see [LICENSE](./LICENSE). Individual template repos are licensed independently
(also MIT) — check each repo before reuse.
