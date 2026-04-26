# Story Bank — Master STAR+R Stories

This file accumulates your best interview stories over time. Each evaluation (Block F) adds new stories here. Instead of memorizing 100 answers, maintain 5-10 deep stories that you can bend to answer almost any behavioral question.

## How it works

1. Every time `/career-ops oferta` generates Block F (Interview Plan), new STAR+R stories get appended here
2. Before your next interview, review this file — your stories are already organized by theme
3. The "Big Three" questions can be answered with stories from this bank:
   - "Tell me about yourself" → combine 2-3 stories into a narrative
   - "Tell me about your most impactful project" → pick your highest-impact story
   - "Tell me about a conflict you resolved" → find a story with a Reflection

## Stories

<!-- Stories will be added here as you evaluate offers -->
<!-- Format:
### [Theme] Story Title
**Source:** Report #NNN — Company — Role
**S (Situation):** ...
**T (Task):** ...
**A (Action):** ...
**R (Result):** ...
**Reflection:** What I learned / what I'd do differently
**Best for questions about:** [list of question types this story answers]
-->

### [Ownership] Wallzoe: SaaS from Zero
**Source:** Report #003 — Metrikflow — Software Engineer (Full Stack)
**S:** Startup needed a social media scheduling + photo editing SaaS with no existing codebase.
**T:** Own the full stack end-to-end — architecture, frontend, backend, billing, team coordination.
**A:** Built React frontend + TypeScript/Node.js/GraphQL/MongoDB backend; integrated Stripe billing and TOAST UI image editor; managed a small cross-functional team; optimized job scheduling across servers.
**R:** Shipped a production multi-feature SaaS with billing, real-time features, and scheduling.
**Reflection:** Full ownership requires ruthless scope cuts. Infinite perfectionism vs. shipping velocity — choosing what NOT to build is the hardest skill.
**Best for questions about:** Full-stack ownership, technical leadership, startup experience, building from scratch, scope management

### [Architecture] SmythOS GenAI LLM Component
**Source:** Report #003 — Metrikflow — Software Engineer (Full Stack)
**S:** SmythOS needed the core "brain" component in the visual workflow builder to be extensible for Classifier, LLM Assistant, Sub-Agent, and agent-as-component flows.
**T:** Design and implement a single component that handled multiple execution modes without a combinatorial explosion of code paths.
**A:** Designed the component API surface, input/output schema, and runtime dispatch; validated with non-technical user testing.
**R:** Became the primary LLM interaction point in the product, used across thousands of workflows.
**Reflection:** Extensibility > cleverness. Simple, predictable component APIs scale better than clever abstractions.
**Best for questions about:** API design, component architecture, extensibility, backend systems

### [Performance] RAG Pagination in sre-builder-debugger
**Source:** Report #003 — Metrikflow — Software Engineer (Full Stack)
**S:** Unbounded vector DB queries caused memory spikes and slow responses in the debug data service.
**T:** Implement pagination without breaking existing API consumers.
**A:** Added cursor-based pagination to the data layer; maintained backwards compatibility via optional query params.
**R:** Eliminated memory spikes; reduced median query response time significantly.
**Reflection:** Pagination is not just a performance feature — it's a correctness contract for data consumers.
**Best for questions about:** Database optimization, performance, backwards compatibility, API design

### [Automation] server-common npm CI/CD Pipeline
**Source:** Report #003 — Metrikflow — Software Engineer (Full Stack)
**S:** SmythOS/server-common was published manually; error-prone and slowed the team down.
**T:** Set up automated GitHub Actions release and publish pipeline for the npm package.
**A:** Wrote the release workflow (ctix + Rollup/esbuild build, version bump, npm publish, GitHub release tag); added test gate before publish.
**R:** Fully automated releases; reduced publish time from 30+ minutes manual to ~3 minutes automated.
**Reflection:** CI/CD is a force multiplier for team trust — engineers ship more when they know a broken publish can't slip through.
**Best for questions about:** CI/CD, DevOps, automation, process improvement, team productivity

### [Integration] Zapier AI Actions as First-Class Components
**Source:** Report #003 — Metrikflow — Software Engineer (Full Stack)
**S:** SmythOS users wanted to trigger Zapier workflows from inside agent flows, but there was no native integration.
**T:** Turn Zapier's AI Actions API into native SmythOS workflow components with drag-and-drop support.
**A:** Integrated Zapier's dynamic action import API; built runtime execution bridge; added auth flow.
**R:** Enabled 1000s of Zapier actions as reusable SmythOS components without any manual registration.
**Reflection:** Third-party API surface varies wildly — build for the worst-case (auth failure, schema change, rate limit) first, not the happy path.
**Best for questions about:** Third-party API integration, product thinking, extensibility, reliability

### [Collaboration] AbortController Across All LLM Providers
**Source:** Report #003 — Metrikflow — Software Engineer (Full Stack)
**S:** Long-running LLM requests had no cancellation path; zombie requests consumed quota with no way to stop them.
**T:** Implement graceful cancellation uniformly across 10+ provider adapters (PR #309).
**A:** Designed a shared AbortController pattern; wrote comprehensive integration tests for each provider; reviewed and merged through PR process.
**R:** Zero-cost request cancellation across all providers; integration tests caught 3 edge cases in streaming paths that would have shipped as bugs.
**Reflection:** Cross-cutting changes need extra test coverage proportional to their blast radius. The investment paid off immediately.
**Best for questions about:** Cross-cutting concerns, testing, code review, reliability engineering
