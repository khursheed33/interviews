Complete GenAI Engineer Preparation Roadmap

This roadmap covers the skills required to become a strong Full-Stack GenAI Engineer, from Python and React.js fundamentals to LLMs, RAG, AI agents, MCP, databases, infrastructure, local deployment, cloud deployment, and production systems.

The goal is to help you prepare for real projects and technical interviews—not just learn AI terminology.

1. Complete technology stack

AI and LLM engineering

LLMs, transformers, prompting, tokenization, embeddings, vector search, RAG, agents, MCP, evaluation, fine-tuning, guardrails.

Backend — Python

Python, OOP, FastAPI, REST APIs, async programming, authentication, background jobs, testing, WebSockets, streaming.

Frontend — React.js

JavaScript/TypeScript, React hooks, components, API integration, chat interfaces, streaming responses, state management, authentication.

Data and storage

PostgreSQL, Redis, DynamoDB, vector databases, document ingestion, object storage, metadata, caching.

Infrastructure and deployment

Linux, Git, Docker, Docker Compose, Nginx, CI/CD, local LLM serving, cloud hosting, secrets, monitoring, scalability.

2. Topics to clear first

Follow this sequence. Do not start by jumping directly into agents or complex RAG frameworks.

The checklist is interactive. Tick topics off as you become confident with them.

Learning progress

0/64

Phase 1 — Programming foundations

0/8 topics · 1–2 weeks

Complete phase

Python syntax, collections and control flow

Functions, modules, exceptions and file handling

OOP, decorators, generators and context managers

Type hints, dataclasses and Pydantic

Iterators, comprehensions and dependency management

Async/await, asyncio, threads and processes

Git, GitHub, terminal and Linux basics

HTTP, JSON, DNS, TCP/IP and client-server architecture

Phase 2 — Frontend foundations

0/8 topics · 1–2 weeks

Complete phase

HTML5, CSS, responsive design and Flexbox/Grid

JavaScript ES6+, promises and async/await

TypeScript fundamentals and interfaces

React components, props and JSX

State, events, useState, useEffect and useRef

Custom hooks, context and component composition

Forms, validation and API calls

Routing, error states, loading states and accessibility

Phase 3 — Backend engineering

0/8 topics · 1–2 weeks

Complete phase

FastAPI routes, request/response models and Pydantic

REST conventions, status codes and API versioning

Dependency injection and middleware

Async endpoints and external API calls

Authentication, authorization, JWT, OAuth2 and RBAC

SQL, ORM, migrations, transactions and indexes

File uploads, pagination, filtering and validation

Pytest, mocking, integration tests and API documentation

Phase 4 — Machine learning and NLP

0/8 topics · 1–2 weeks

Complete phase

Supervised, unsupervised and self-supervised learning

Train, validation and test splits; overfitting and leakage

Vectors, matrices, dot product, cosine similarity and norms

Probability, distributions and basic statistics

Neural networks, loss functions, gradient descent and backpropagation

NLP, tokenization, vocabulary and subword tokens

Transformers, attention, self-attention and positional encoding

Encoder, decoder, encoder-decoder and inference

Phase 5 — LLM foundations

0/8 topics · 1 week

Complete phase

LLM architecture and model families

Pretraining, instruction tuning, SFT and RLHF/DPO concepts

System, developer and user instructions; prompt structure

Context windows, tokens, latency, throughput and cost

Temperature, top-p, max output tokens and stop sequences

Structured outputs, JSON schemas and tool/function calling

Hallucinations, grounding and model limitations

Model selection: quality, context, cost, latency and licensing

Phase 6 — Embeddings and RAG

0/8 topics · 1–2 weeks

Complete phase

Embedding models and vector representations

Chunking by size, overlap, structure and semantics

Document parsing, cleaning and metadata extraction

Vector databases, indexes, distance metrics and filtering

Dense retrieval, BM25 and hybrid search

Top-k retrieval, reranking and contextual compression

RAG pipelines, citations and source attribution

Retrieval evaluation, answer evaluation and failure analysis

Phase 7 — Agents and MCP

0/8 topics · 1–2 weeks

Complete phase

Tool calling and typed tool schemas

Agent loop: plan, act, observe and stop

Workflows versus autonomous agents

State, memory, checkpoints and conversation history

Single-agent and multi-agent architecture trade-offs

MCP hosts, clients, servers and protocol concepts

MCP tools, resources, prompts and transports

Approvals, permissions, timeouts, retries and agent safety

Phase 8 — Production GenAI

0/8 topics · 1–2 weeks

Complete phase

Redis caching and request deduplication

Queues, workers, retries and idempotency

LLM observability, tracing and token-cost tracking

RAG/agent evaluation datasets and regression tests

Prompt injection and indirect prompt injection

PII handling, access control and tenant isolation

Rate limits, circuit breakers and fallback models

Docker, CI/CD, deployment, monitoring and incident response

Reset checklist

These phases are a suggested sequence, not a requirement to master every mathematical detail before building applications. Start implementing small projects alongside your learning.

3. Python backend — topics and subtopics

Learn these well enough to design and build APIs without relying entirely on AI-generated code.

Main topic	Subtopics to master
Python core	Collections, functions, scope, exceptions, comprehensions, modules
Advanced Python	Decorators, generators, iterators, context managers, typing, dataclasses
Async programming	Coroutines, asyncio, await, gather, semaphores, cancellation, timeouts
FastAPI	Routers, Pydantic, dependency injection, middleware, lifespan, OpenAPI
API engineering	REST, HTTP methods, status codes, pagination, filtering, idempotency
Security	OAuth2, JWT, password hashing, RBAC, CORS, API keys, secret management
Database	SQL, joins, transactions, indexes, connection pooling, migrations
Background processing	Task queues, workers, retries, scheduled jobs, dead-letter queues
Testing	Pytest, fixtures, mocks, async tests, integration and contract tests
Performance	Profiling, caching, concurrency limits, connection reuse, rate limiting
Production	Structured logging, exception handling, health checks, metrics, tracing

Libraries to know: FastAPI, Pydantic, SQLAlchemy, Alembic, httpx, pytest, boto3, Redis client and a PostgreSQL driver.

Important practical problems:

* Preventing multiple users from triggering duplicate synchronization jobs.
* Processing thousands of paginated records without holding everything in memory.
* Handling API timeouts, retries, rate limits and partial failures.
* Streaming LLM responses to a React frontend.
* Managing long-running document ingestion jobs.
* Storing conversation history without repeatedly sending unnecessary context to the LLM.

4. React.js frontend — topics and subtopics

Main topic	Subtopics to master
JavaScript	ES6+, destructuring, modules, promises, async/await, closures
TypeScript	Types, interfaces, unions, generics, type narrowing
React fundamentals	Components, JSX, props, state, events, rendering
Hooks	useState, useEffect, useRef, useMemo, useCallback, custom hooks
State management	Context, reducers, Zustand or Redux Toolkit when appropriate
API integration	Fetch/Axios, request cancellation, error handling, loading states
Forms	Controlled inputs, validation, file uploads, multi-step forms
Routing	React Router, protected routes, query parameters
Styling	CSS, Flexbox, Grid, responsive design, Tailwind CSS
Authentication	Login, token/session management, logout, permissions
Testing	Vitest or Jest, React Testing Library, Playwright
Performance	Lazy loading, code splitting, memoization, virtualization
Accessibility	Keyboard navigation, labels, focus management, ARIA

GenAI-specific frontend skills

These are especially important because a standard CRUD frontend is not enough for an AI application.

* Chat UI with conversation history and message roles.
* Streaming text using Server-Sent Events (SSE) or WebSockets.
* Stop-generation and retry controls.
* Markdown rendering, syntax-highlighted code and tables.
* Source citations with clickable document references.
* File upload, processing status and document deletion.
* Tool-call and agent execution status.
* Human approval interfaces for sensitive agent actions.
* Token usage, latency and feedback indicators.
* Handling reconnects, interrupted streams and duplicate submissions.

Suggested stack: React + TypeScript + Vite, React Router, TanStack Query, and Tailwind CSS. Add a state library when the application actually needs it.

5. LLM models — understand the full landscape

An LLM is the model that generates or reasons over text and other supported inputs. The API provider, model, orchestration framework and application are separate things.

A. Model architecture

* Transformers and attention mechanisms
* Encoder-only, decoder-only and encoder-decoder models
* Dense models versus mixture-of-experts (MoE)
* Context length and positional encoding
* Pretraining versus instruction tuning
* Quantization and inference

B. Tokenization and generation

* BPE, WordPiece and SentencePiece concepts
* Token IDs, embeddings and output logits
* Sampling, temperature and top-p
* Context-window limits
* Prompt tokens versus generated tokens
* Time to first token and tokens per second

C. Model selection

* General-purpose chat models
* Reasoning-oriented models
* Coding models
* Vision-language and multimodal models
* Small language models (SLMs)
* Open-weight versus proprietary models
* Context length, licensing, latency, cost and quality trade-offs

Model families worth studying

Examples of model families you may encounter include:

* OpenAI GPT — general-purpose and reasoning-capable models.
* Google Gemini — multimodal models and long-context applications.
* Anthropic Claude — general-purpose, coding and tool-use workflows.
* Meta Llama — open-weight model family.
* Qwen — language, coding and multimodal model families.
* Mistral — general-purpose and smaller deployable models.
* DeepSeek — reasoning and coding-oriented model families.
* Gemma — open-weight models from Google.
* Whisper — speech recognition, rather than a general chat LLM.

Learn the difference between model weights, a model checkpoint, an inference server, an API endpoint and an orchestration framework. They are not interchangeable.

6. Embedding models and vector search

An embedding model converts text, images or other supported inputs into numerical vectors. Those vectors help retrieve content with similar meaning.

Example: semantic search

Query

“How do I reset my password?”

Embedding model

Converts the query into a vector, such as 0.12, -0.08, ....

Vector search

Finds related content such as “Account password recovery instructions.”

Embedding topics

* Dense vectors, dimensions and similarity.
* Cosine similarity, dot product and Euclidean distance.
* Query and document embedding compatibility.
* Chunking strategies and overlap.
* Embedding normalization.
* Batch embedding, rate limits and retries.
* Multilingual and domain-specific embeddings.
* Vector indexes, approximate nearest-neighbor search and filtering.
* Re-embedding when a model or document changes.
* Measuring retrieval precision and recall.

Embedding models to know

Model	What to understand
BAAI/bge-small-en-v1.5	Compact English text embeddings
BAAI/bge-base-en-v1.5	A larger English embedding model
BAAI/bge-m3	Multilingual and multi-function retrieval
intfloat/e5-small-v2	Compact text retrieval embeddings
sentence-transformers/all-MiniLM-L6-v2	Lightweight semantic search
nomic-embed-text	Embeddings suitable for local workflows
text-embedding-3-small	Hosted embeddings through the OpenAI API
gemini-embedding family	Hosted embeddings; check the currently supported model ID

The exact model you select should depend on language, retrieval quality, vector dimensions, licensing, hardware and provider support. Not every model works with every hosted API.

7. RAG — Retrieval-Augmented Generation

RAG connects an LLM to external knowledge so it can answer using relevant documents rather than relying only on information learned during training.

Document sources

PDFs · DOCX · Excel · HTML · SharePoint · databases

Ingestion pipeline

Extract → clean → chunk → add metadata

Embedding and indexing

Generate vectors → store chunks → index

Retrieval

Search → filter → rerank → select context

LLM response

Answer grounded in retrieved context, with citations where supported

RAG syllabus

1. Document ingestion

* PDF parsing, OCR and tables.
* Word, Excel, HTML and Markdown parsing.
* Document identifiers, versions, timestamps and permissions.
* Incremental ingestion, deletion and re-indexing.

2. Chunking

* Fixed-size and overlapping chunks.
* Recursive and structure-aware chunking.
* Semantic chunking.
* Parent-child retrieval and hierarchical chunking.

3. Retrieval

* Dense vector retrieval.
* Sparse search and BM25.
* Hybrid retrieval.
* Metadata and permission filtering.
* Query rewriting, multi-query retrieval and reranking.

4. Generation

* Context construction.
* Prompt templates.
* Grounding and abstaining when evidence is insufficient.
* Citation generation and source verification.

5. Advanced RAG

* Corrective and self-reflective retrieval patterns.
* Graph-based RAG.
* Agentic RAG.
* Multimodal RAG.
* Query routing and multi-index retrieval.

6. Evaluation

* Retrieval precision, recall and hit rate.
* MRR and nDCG.
* Faithfulness, answer relevance and context relevance.
* Latency, token costs and end-to-end success rate.

Critical distinction: RAG does not normally retrain the LLM. It retrieves relevant information at inference time. Fine-tuning changes model behavior or parameters through training; it is a different technique.

8. AI agents and agentic workflows

An agent is an LLM-powered system that can select tools, take actions, inspect results and continue toward a goal. A production agent also needs explicit limits and permissions.

Concepts you must understand

Topic	Subtopics
Tool calling	Function schemas, argument validation, tool results, errors
Agent loop	Observe, decide, act, inspect, stop
Planning	Task decomposition, dependency ordering, replanning
Memory	Conversation history, session state, persistent memory, summaries
Workflows	Sequential, parallel, conditional and human-in-the-loop
State management	Checkpoints, resumability, durable execution
Multi-agent systems	Supervisor, specialist agents, handoffs, shared state
Agent reliability	Max steps, timeouts, retries, budgets, termination conditions
Agent evaluation	Task completion, tool accuracy, efficiency, failure rates
Security	Least privilege, approval gates, prompt injection, audit logs

Frameworks to learn

LangChain

Learn model integrations, prompts, retrievers, tools and common orchestration abstractions.

LangGraph

Learn stateful graphs, conditional edges, checkpoints, human approval and resumable agent workflows.

LlamaIndex

Learn document ingestion, data connectors, indexes, retrieval and agentic knowledge applications.

Microsoft AutoGen

Study multi-agent conversations and orchestration concepts. Also understand the newer Microsoft agent development ecosystem before selecting a framework for a new project.

Do not learn every framework at once. Start with direct Python tool calling, then one workflow framework such as LangGraph. Learn how to implement the same workflow without a framework so you understand what the framework is doing.

9. MCP — Model Context Protocol

MCP is a standard protocol for connecting AI applications to external tools and data sources. It is not an LLM, an embedding model or a replacement for RAG.

MCP architecture

AI application / host

Chat UI, IDE or agent application

MCP client

Manages the protocol connection to an MCP server

MCP server

Exposes tools, resources and prompts

Tools

Actions and functions

Resources

Context and data

Prompts

Reusable templates

MCP topics and subtopics

* Protocol architecture, JSON-RPC and message lifecycle.
* Hosts, clients, servers and capability negotiation.
* Tools, resources, prompts and discovery.
* Local stdio transport and remote Streamable HTTP.
* Server initialization, sessions where applicable, and error handling.
* Authentication, OAuth concepts, scopes and access control.
* Python MCP SDK and TypeScript MCP SDK.
* Connecting an agent to one or more MCP servers.
* Tool schemas, validation and result handling.
* Timeouts, server disconnections and reconnection.
* User consent, confirmation before sensitive operations and audit trails.
* MCP security risks, including malicious tool descriptions and untrusted output.

Build these MCP projects

* A local filesystem MCP server with restricted read-only access.
* A database MCP server with safe, parameterized queries.
* A RAG MCP server that searches documents and returns source references.
* A client that discovers tools and exposes them to an LLM.
* An agent that uses two MCP servers, handles failures and requests human approval for write operations.

Remember: MCP standardizes how the application connects to tools and data; the LLM still needs an orchestration loop or application logic to decide what to do with them.

10. Vector databases and traditional databases

Learn both relational storage and vector retrieval. Most real applications need both.

Technology	Topics to learn
PostgreSQL	Tables, joins, indexes, transactions, JSONB and migrations
pgvector	Vector columns, similarity operators, indexes and metadata filters
Chroma	Local prototyping, collections, metadata and vector search
Qdrant	Collections, payload filtering, indexes and hybrid retrieval
Pinecone	Managed vector database, namespaces and filtering
Weaviate	Collections, vectorization and hybrid search
FAISS	Local similarity search and approximate nearest-neighbor indexes
Redis	Caching, TTLs, locks, rate limits, queues and ephemeral state
DynamoDB	Partition/sort keys, conditional writes, TTL, streams and atomic updates

Understand when you need a dedicated vector database versus PostgreSQL with pgvector. Start with PostgreSQL + pgvector or Chroma locally, then compare alternatives when you have measurable requirements.

Also learn document stores and object storage: S3-compatible storage, document metadata, versioning, content hashes and deletion propagation.

11. Free API keys and development services

You can build a useful GenAI portfolio without paying for a large hosted model. Free tiers have quotas and may change, so verify current limits before designing around them.

Groq

Fast hosted inference for supported language and vision models. Useful for chat, tool-calling experiments and streaming.

Get started: Groq Console⁠￼ · Check model-specific rate limits and API availability.

Gemini API

Hosted models for text and multimodal tasks. Selected models have a free tier, with usage and data-use conditions.

Get started: Google AI Studio⁠￼ · Official pricing and free-tier details⁠￼. Google AI for Developers

OpenRouter

A convenient way to experiment with multiple providers using one API interface. Free model variants are available, subject to rate limits and model-specific availability.

Get started: OpenRouter⁠￼ · Browse free models⁠￼. OpenRouter +1

Hugging Face

Explore model checkpoints, embedding models, datasets and hosted inference. Free inference credits are limited and subject to change.

Get started: Hugging Face⁠￼ · Inference pricing⁠￼. Hugging Face +1

Ollama

Run supported open-weight models locally. Great for privacy-focused demos, learning inference and avoiding hosted inference charges when your hardware is adequate.

Get started: Ollama⁠￼ · API documentation⁠￼. GitHub

Cerebras

Another hosted inference option worth testing for speed and model availability. Verify current developer access, quotas and free-tier terms.

Get started: Cerebras Cloud⁠￼.

What about embeddings for free?

For a zero-cost local embedding pipeline, start with sentence-transformers/all-MiniLM-L6-v2 or a compatible BGE model through Sentence Transformers. Model weights can be downloaded and run locally, subject to the model’s license and your hardware.

For hosted embeddings, check the selected provider’s current API support and pricing. Do not assume a free chat API key also provides free embedding access. Chat generation and embedding generation may be separate endpoints with separate limits.

Recommended starter combination

* Chat model: Groq or a currently free OpenRouter model.
* Alternative multimodal model: Gemini API free tier, if the required feature is available.
* Local LLM: Ollama.
* Local embeddings: Sentence Transformers.
* Vector store: Chroma or PostgreSQL + pgvector.
* Backend: FastAPI.
* Frontend: React + TypeScript.
* Deployment: Docker Compose on your laptop first.

Never expose provider API keys in React code or commit them to Git. Store keys in backend environment variables or a secrets manager.

12. Local infrastructure and deployment

You should be able to take a GenAI project from your laptop to a repeatable, deployable application.

Infrastructure syllabus

Area	Topics and subtopics
Operating systems	Linux commands, processes, permissions, environment variables
Git	Branching, pull requests, merge conflicts, tags, release management
Python environments	venv, pip, pyproject.toml, dependency locking
Docker	Images, containers, layers, volumes, networks, health checks
Docker Compose	Multi-service applications, service discovery, dependencies, environment files
Reverse proxy	Nginx, TLS, routing, headers, request size limits
CI/CD	GitHub Actions, linting, testing, image builds, deployment pipelines
Configuration	Development/staging/production configs, secrets, configuration validation
Observability	Logs, metrics, traces, dashboards, alerts
Cloud fundamentals	Compute, storage, networking, IAM, managed databases
Scaling	Load balancing, horizontal scaling, worker pools, autoscaling
Reliability	Backups, restore testing, retries, circuit breakers, disaster recovery

Learn these deployment patterns

Start here

Level 1 — Everything local

React + FastAPI + PostgreSQL/pgvector + Ollama + Docker Compose.

Goal: Run the entire application with one repeatable setup. No paid API is required if you run a suitable local model.

Level 2 — Hybrid application

React + FastAPI + local vector database + hosted LLM API.

Goal: Understand API keys, rate limits, network failures, provider switching and cost tracking.

Level 3 — Production-style deployment

React hosting + FastAPI container + managed database + object storage + background worker + monitoring.

Goal: Authentication, HTTPS, durable jobs, database migrations, backups, logs, alerts and secure secrets.

Local LLM serving

Learn these concepts and tools:

* Ollama: downloading, running and serving local models.
* Hugging Face Transformers: loading checkpoints and running inference.
* llama.cpp: quantized model inference and CPU/GPU trade-offs.
* vLLM: higher-throughput model serving on supported hardware.
* OpenAI-compatible APIs: standardizing application integrations across compatible providers.
* GPU versus CPU inference, VRAM requirements, quantization and batching.

You do not need all these tools on day one. Begin with Ollama and move to a more advanced serving engine when you understand why your workload needs it.

Suggested project structure

genai-platform/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── hooks/
│   │   ├── services/
│   │   └── types/
│   ├── package.json
│   └── Dockerfile
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── core/
│   │   ├── models/
│   │   ├── schemas/
│   │   ├── repositories/
│   │   ├── services/
│   │   ├── llm/
│   │   ├── rag/
│   │   ├── agents/
│   │   └── mcp/
│   ├── tests/
│   ├── pyproject.toml
│   └── Dockerfile
├── infrastructure/
│   ├── nginx/
│   └── scripts/
├── docker-compose.yml
├── .env.example
├── .gitignore
└── README.md

Keep provider-specific logic inside an LLM service layer. This lets you change between hosted providers and local models without rewriting the entire application.

13. Additional skills that separate a junior from a strong GenAI engineer

A. Evaluation and observability

* Golden test datasets for RAG and agent workflows.
* Retrieval metrics versus answer-quality metrics.
* Model-as-judge limitations and human evaluation.
* Prompt and model version tracking.
* Traces showing retrieval, tool calls, model calls and failures.
* Token usage, latency, throughput and cost per request.
* Regression testing after changing prompts, chunking or models.
* A/B testing and controlled rollouts.

Useful tools to explore include Langfuse, OpenTelemetry, MLflow, and Phoenix from Arize.

B. Security and responsible AI

* Prompt injection and indirect prompt injection.
* Sensitive-data leakage and PII redaction.
* Authentication, authorization and document-level access controls.
* SQL injection, SSRF, unsafe file uploads and insecure deserialization.
* Tool allowlists and restricted execution environments.
* Human approval for financial, destructive or external actions.
* Tenant isolation in multi-user RAG systems.
* Retention, deletion, audit logging and model-provider data policies.
* Supply-chain risks, dependency scanning and secret scanning.

Treat retrieved documents and tool outputs as untrusted input. Never let an agent gain unrestricted database, shell or filesystem access merely because an LLM requested it.

C. Advanced AI topics

Learn these after you can build a reliable RAG application.

* Fine-tuning: supervised fine-tuning, LoRA and QLoRA.
* Preference optimization: RLHF and DPO concepts.
* Model quantization: FP16, BF16, INT8 and INT4 trade-offs.
* Reranking models and cross-encoders.
* Graph RAG and knowledge graphs.
* Multimodal systems: vision, audio, OCR and document understanding.
* Speech-to-text and text-to-speech.
* Model routing and fallback strategies.
* Distillation and small language models.
* Synthetic data, benchmark design and dataset quality.
* GPU memory, batching, KV caching and inference optimization.

You do not need to train a foundation model from scratch to be a competent GenAI engineer.

14. Build projects in this order

These projects cover the concepts above in a practical sequence.

Project 1 — Full-stack AI chat

Beginner

Build a React chat interface backed by FastAPI and a hosted or local LLM.

* Streaming responses, chat history and error handling.
* Provider abstraction and environment-based configuration.
* Token usage and basic tests.

Project 2 — Document Q&A with RAG

Intermediate

Upload PDFs, Word documents and Excel files, then ask questions about them.

* Ingestion, chunking, embeddings and vector search.
* Source citations, access control and document deletion.
* Retrieval evaluation and insufficient-evidence handling.

Project 3 — Tool-using AI agent

Intermediate

Build an agent that calls search, calculator and database tools.

* Typed arguments and validated outputs.
* State, tool execution, retries and termination limits.
* Approval before write operations and an audit trail.

Project 4 — MCP integration

Build an MCP server and connect it to an LLM-powered client.

* Expose tools and resources.
* Discover and invoke tools.
* Handle authentication, permissions and server failures.

Project 5 — Production-ready knowledge assistant

Portfolio capstone

Build a multi-user knowledge assistant with background ingestion, document permissions, hybrid retrieval and agent tools.

* React + FastAPI + PostgreSQL/pgvector + Redis.
* Docker Compose, CI/CD, monitoring and automated tests.
* Incremental document synchronization, duplicate-job prevention, evaluation and deployment.

For the capstone, include a short architecture document, sequence diagrams, API documentation, a setup guide, a demo and a list of trade-offs. These are useful in both interviews and portfolio reviews.

15. A practical 12-week preparation plan

Assuming you can study approximately 1.5–2 hours daily alongside work:

Week	Primary focus	Deliverable
1	Python, Git, Linux, HTTP	Python utilities and tested functions
2	React, JavaScript, TypeScript	Small React application
3	FastAPI, SQL, auth, testing	Secure REST API
4	ML, NLP, transformers and LLM concepts	Model comparison and prompt experiments
5	Embeddings, chunking, vector search	Local semantic-search application
6	RAG, hybrid search, reranking and evaluation	Document Q&A application
7	Tool calling, agent loops and state	Tool-using agent
8	MCP and workflow orchestration	MCP server and connected client
9	PostgreSQL, Redis, jobs and idempotency	Reliable ingestion pipeline
10	Docker, local models and CI/CD	Repeatable local deployment
11	Security, observability and evaluation	Tested, instrumented application
12	Capstone polish and interview revision	Deployable portfolio project

If your Python and React foundations are already strong, spend less time on the early weeks and more on RAG evaluation, agents, MCP, reliability and infrastructure.

16. Interview preparation checklist

By the end, you should be able to answer these questions without memorizing definitions alone.

LLMs and embeddings

How does a transformer generate text?

What is the difference between an LLM and an embedding model?

How do temperature and top-p affect output?

What are quantization and context-window limits?

RAG

Explain the complete ingestion and query pipelines.

How do you choose chunk size and overlap?

When do you use hybrid search or reranking?

How do you evaluate retrieval quality and answer faithfulness?

Agents and MCP

What is the difference between an agent and a deterministic workflow?

How does tool calling work?

What are MCP hosts, clients, servers, tools and resources?

How do you stop an agent from looping or executing unsafe actions?

Full-stack engineering

How do you stream LLM output to React?

How do you implement authentication and authorization?

How do you handle timeouts, retries and duplicate requests?

How do you test asynchronous FastAPI endpoints?

Infrastructure and production

How would you deploy a local LLM and a hosted LLM application?

How do you monitor token cost, latency and errors?

How do you secure API keys and document access?

How do you handle 20,000+ document records without duplicate jobs?

0 of 16 questions revised.

17. Final priority order

If you want the shortest path to becoming productive as a Full-Stack GenAI Engineer, prioritize these in order:

* Python + FastAPI + React + TypeScript
* LLM fundamentals + prompt engineering + structured outputs
* Embeddings + vector databases + RAG
* Tool calling + agents + workflow orchestration
* MCP + integrations + permission management
* SQL + Redis + background jobs + reliable APIs
* Docker + local model serving + deployment
* Evaluation + observability + security
* Fine-tuning + multimodal AI + advanced inference optimization

You do not need to master every framework or database. You do need to understand the underlying concepts well enough to select the right tool, explain your design choices, debug failures and ship a working application.

Your target outcome: one polished React + Python GenAI application that includes RAG, at least one tool-using agent, an MCP integration, a local deployment option, automated tests and a documented architecture. That single project can demonstrate a substantial portion of this roadmap.