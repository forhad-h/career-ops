# CV -- Forhad Hosain

**Location:** Natore Sadar, Natore - 6400, Bangladesh
**Phone:** 01744351150
**Email:** forhad19s@gmail.com
**LinkedIn:** linkedin.com/in/forhad-hosain-20a734147
**GitHub:** github.com/forhad-hosain

## Professional Summary

Full Stack Engineer with 6+ years building production SaaS and AI products across TypeScript, Node.js, and React. At INK Content, Inc. (SmythOS), contributed 660+ commits and 96+ merged PRs across three production open-source repositories — spanning the shared LLM provider integration layer, visual agent builder UI, and agent embodiment systems. Hands-on with multi-provider LLM integrations (OpenAI, Anthropic, Google AI, xAI, Groq, Perplexity, Amazon Bedrock, Google Vertex AI), streaming systems, structured output, tool/function calling, and agentic AI runtimes. Earlier experience includes GraphQL SaaS platforms, WordPress plugins, and remote product development across startups.

## Work Experience

### INK Content, Inc. -- Remote
**Full Stack Developer**
April 2022 – April 2026

#### SmythOS (AI Agent Platform)
July 2023 – April 2026

Core developer on the SmythOS agentic AI platform — "the Linux of AI agents" — competing with LangChain and AutoGen. Work spans three open-source repositories (publicly verifiable by commit history) plus three internal services, covering the entire stack from LLM provider integrations to the visual agent builder UI and agent embodiment interfaces.

**Shared LLM Provider Integration Layer (SmythOS/sre — 1,248 stars):**
- Co-implemented a production-grade fallback/proxy layer for custom LLM models so agents can fall back across providers without user intervention (PRs #310, #312)
- Implemented cross-provider function/tool calling in both non-streaming and streaming responses, keeping agent behavior consistent across all provider adapters
- Standardized the event-emitter pattern (never-throw, always-emit) across provider integrations for consistent, resilient error handling
- Introduced `TLLMFinishReason` enum across all providers for uniform stream-termination handling, eliminating provider-specific parsing throughout the codebase
- Implemented AbortController-based graceful request cancellation across all provider integrations with comprehensive integration tests (PR #309)
- Added native structured output and extended reasoning/thinking model support (budget_tokens management, tool-choice enforcement) for Anthropic models (PRs #327, #328)
- Integrated new AI providers: xAI/Grok (with real-time web search), Perplexity AI, Google Imagen 4, OpenAI Responses API, Groq reasoning models, Amazon Bedrock, Google Vertex AI
- Built end-to-end image generation pipeline (DALL-E, Google Imagen 4, Runware, GPT Image) with usage tracking, binary I/O handling, and base64 processing supporting up to 4K resolution (~30 MB) images (PR #352)
- Designed token usage reporting system tracking input/output/cached tokens and image generation costs per provider to support billing and quota enforcement at scale
- Implemented dynamic model configuration hot-loading without runtime restarts, improving deployment agility
- Fixed critical infinite-tool-call loop in Gemini; added configurable max-tool-calls-per-session limit to prevent runaway agent executions
- Implemented SQLite data connector enabling agents to read/write local databases (PR #301)

**Visual Agent Builder (SmythOS/smythos-studio — 78+ stars):**
- Architected and built the entire standalone `runtime` package from scratch: runtime server, embodiment routes, agent-runner, code sandbox, env configuration, and build pipeline — enabling agents to deploy locally or on the edge independently of the cloud platform
- Designed and shipped the complete UI flow for registering user-owned custom LLM models (provider/feature selection, context window, API key management); validated with LM Studio, Ollama, and Google Colab
- Built reasoning-effort UI controls for GPT-5 family, Claude, and Gemini models; introduced mutual-exclusive field validation to prevent invalid parameter combinations; auto-hid temperature/top-P when reasoning mode is active (PRs #456, #469, #492)
- Did much of the implementation work on the GenAI LLM component — the main LLM "brain" component in the workflow builder — powering Classifier, LLM Assistant, Sub-Agent, and agent-as-component flows
- Built Hugging Face Inference component with inference-only model filtering, cached model discovery/search, and task-schema-driven adaptive field rendering
- Built a generic API Call component enabling agents to make arbitrary HTTP requests (configurable method, URL, headers, auth, binary/file handling) — foundation for many SmythOS integrations
- Turned Zapier AI Actions into first-class workflow components with dynamic action import and full runtime execution support
- Resolved settings-rendering lag for large datasets via lazy/deferred rendering; built Docker-based public models sync container to decouple model releases from full app deployments

**Agent Embodiment Library (SmythOS/server-common — top contributor, 56% of all PRs):**
- Primary contributor: 59 commits, 19 of 34 merged PRs — refactored, tested, and productionized 9 of 11 server roles for reuse across SmythOS distributions
- Roles shipped: Postman, ChatGPT, OpenAI-compatible API, OpenAPI, Alexa, MCP, Voice, Form Preview, Chat (with LLM context store, streaming, conversationID/agentId handling)
- Contributed to the `BaseRole` resolver pattern (`Resolvable<T, Args>` type letting any role option accept a static value or a dynamic function)
- Set up GitHub Actions CI/CD release and publish pipeline for the npm package

**Internal Services:**
- Contributed to sre-agent-server (OAuth 2.0 + PKCE, JWT/OIDC, Redis-backed session management, rate limiting, billing enforcement)
- Contributed to sre-embodiment-server (multi-protocol agent exposure: chat, OpenAI-compatible API, ChatGPT plugin, Alexa, MCP, voice)
- Implemented pagination for RAG/vector DB queries in sre-builder-debugger data service

#### INK (AI SEO Writing Assistant)
April 2022 – April 2026

- Served as key maintainer, ensuring application stability over 4 years
- Enhanced the web-based text editor: integrated SEO optimization system, plagiarism detection, and real-time grammar checking via Grammarly
- Implemented content change trigger logic, document methods layer, and IndexedDB-based client-side document storage
- Used MQTT for real-time document synchronization across clients
- Built ink-score API caching layer and optimized cache keys to reduce redundant API calls across inkjs (embeddable UI library)

---

### Freelance Full Stack Developer -- Remote
January 2020 – February 2022

- **Wallzoe** — Full technical ownership of a SaaS social media scheduling and photo editing platform. Led a small cross-functional team; built a responsive React frontend and scalable TypeScript/Node.js/GraphQL/MongoDB backend; integrated Stripe billing, enhanced TOAST UI Image Editor, and optimized job scheduling across servers
- Developed a WordPress plugin integrating Thrive Apprentice with Ultimate Membership Pro for drip-fed course access based on subscription plans
- Built a custom plugin connecting Paddle payments with Ultimate Affiliate Pro via REST API for automated affiliate registration and referral tracking
- Created a web-based time tracker leveraging the Timular platform
- Extended BuddyBoss to develop a habit-building social platform

---

### eeExpert -- Bangladesh
**Web Developer**
March 2018 – April 2020

- Built custom WordPress themes and plugins tailored to client needs
- Built responsive HTML templates
- Contributed to a full-featured web application using Laravel and Vue.js

## Notable Projects

All SmythOS work below was done as a paid employee at INK Content, Inc. — publicly verifiable via commit history and merged PR records on GitHub.

- **[SmythOS/sre](https://github.com/SmythOS/sre)** — SmythOS Runtime Environment. Core developer at INK Content, Inc. (Jun 2025 – Apr 2026): 401+ commits | 55+ PRs | TypeScript | Shared LLM provider integration layer | Agentic AI runtime. 1,248 stars | 190+ forks
- **[SmythOS/smythos-studio](https://github.com/SmythOS/smythos-studio)** — Visual AI Agent Builder. Core developer at INK Content, Inc. (Aug 2025 – Apr 2026): 201+ commits | 22+ PRs | TypeScript/React | Visual agent builder | Standalone runtime package. 78+ stars | 20+ forks
- **[SmythOS/server-common](https://github.com/SmythOS/server-common)** — Shared Agent Embodiment Library (`@smythos/server-common` on npm). Primary contributor at INK Content, Inc. (Oct 2025 – Feb 2026): 59 commits | 19/34 PRs (56%) | TypeScript | Express roles system | MCP | Alexa | OpenAI | Voice | Chat | CI/CD pipeline

## Education

- B.Sc. Electrical & Electronics Engineering, Rajshahi Science & Technology University, Bangladesh (Sep 2018 – May 2022)
- Diploma in Engineering — Electrical, Rajshahi Polytechnic Institute, Bangladesh (2009 – 2014)

## Skills

- **Languages:** TypeScript, JavaScript, Python, PHP
- **Frontend:** React, Next.js, Vue.js, Redux, Tailwind CSS, Material-UI (MUI), HTML/CSS
- **Backend:** Node.js, GraphQL, REST, WebSockets, SSE, Express.js, RabbitMQ
- **Databases:** MongoDB, MySQL, SQLite, Redis, IndexedDB
- **Cloud / Infra:** AWS (S3, Bedrock), Google Vertex AI, Docker, Kubernetes, CloudFlare
- **AI Integration:** OpenAI, Anthropic Claude, Google AI (Gemini + Imagen), xAI/Grok, Perplexity, Groq, Together AI, Hugging Face, Runware, Amazon Bedrock; structured output, tool/function calling, streaming (SSE/WebSocket), AbortController, token usage tracking, model aliasing, model hot-loading, finish reason normalization, agentic runtimes, RAG, MCP, multi-modal (text + image + voice)
- **Auth & Identity:** OAuth 2.0 + PKCE, JWT/OIDC, Logto, Redis-backed session management, rate limiting
- **Testing & CI/CD:** Vitest, GitHub Actions, Docker, ctix, Rollup, esbuild
- **APIs & Integrations:** Stripe, Zapier, Postman, Grammarly, Facebook/Instagram/X/LinkedIn APIs, Amazon Alexa, ChatGPT plugins/actions, OpenAPI/Swagger
- **AI Dev Tools:** Claude Code, Cursor
- **Other:** WordPress (custom themes/plugins), Shopify, web scraping
