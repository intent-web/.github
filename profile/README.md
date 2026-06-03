<p align="center">
  <img src="./logo-text.png" alt="IntentWeb logo" width="720">
</p>

# IntentWeb

**The AI-native layer of the Internet.**

IntentWeb is a vision for a web where websites, applications, APIs, services and organizations are not only readable by humans and crawlable by search engines, but also understandable and safely usable by AI agents.

In the traditional web, a person opens pages, reads content, clicks buttons, fills forms and confirms actions. In the IntentWeb, an AI agent can discover what a website officially offers, understand the rules, check whether an action is safe, ask for user consent when required and execute the task through a clear technical contract.

> From websites to capabilities. From clicks to intents. From SEO to AIO.

## What Is IntentWeb?

**IntentWeb is a proposed web layer where user intent becomes the starting point.**

Instead of forcing an AI agent to guess meaning from visual pages, a website can publish machine-readable information about:

- **Identity** - who owns or operates the website.
- **Knowledge** - which trusted content, products, services, catalogs and policies are available.
- **Capabilities** - what an agent can do, such as search, compare, request, book or prepare an order.
- **Policies** - what is allowed, forbidden or requires consent.
- **Trust** - how authenticity, provenance and auditability are handled.
- **Actions** - how tasks can be executed through OpenAPI, MCP, REST or other controlled endpoints.

For a non-technical reader: IntentWeb is like giving every website an official instruction manual for AI assistants. The assistant does not need to poke around the site like a human. It can read the website's declared capabilities and follow the rules.

## Why It Matters

AI agents are becoming capable of searching, comparing, planning and acting on behalf of users. But today's web was mostly designed for people looking at screens.

That creates a problem:

- Agents must interpret HTML, layouts, buttons, popups and forms.
- Important business rules are often hidden across pages.
- Browser automation breaks when a website redesigns its interface.
- Agents may not know which actions are low-risk, legally binding or payment-related.
- Websites rarely expose clear machine-readable rules for consent, privacy and safe execution.

IntentWeb proposes a cleaner model: **websites should describe themselves explicitly to AI agents.**

## The Core Shift

| Traditional Web | IntentWeb |
| --- | --- |
| Page | Capability |
| Navigation | Discovery |
| Click flow | Intent flow |
| HTML form | Typed input schema |
| Visual interpretation | Machine-readable policies |
| Checkout button | Transaction capability with explicit consent |
| SEO | AIO - Agent Interface Optimization |

Traditional flow:

```text
Page -> Click -> Form -> Checkout
```

IntentWeb flow:

```text
Intent -> Capability -> Policy -> Consent -> Action -> Verifiable Result
```

## Agent Interface Optimization

**AIO, or Agent Interface Optimization, is the practice of preparing a website for AI agents.**

SEO helped websites become easier for search engines to crawl, understand and rank. AIO adds a new layer for AI agents:

| Layer | Purpose |
| --- | --- |
| Human Web | HTML, CSS, UX, forms, checkout and visual design |
| Search Web | `sitemap.xml`, `robots.txt`, metadata, Schema.org and SEO |
| API Web | REST, GraphQL, OpenAPI, webhooks and integrations |
| Agent Web | Agent Manifest, capabilities, policies, consent, trust and actions |

IntentWeb does not replace SEO, APIs or normal websites. It complements them.

## Three Building Blocks

### 1. IntentWeb - the vision

IntentWeb is the overall concept: an AI-native web based on user intent, declared capabilities, explicit policies and trusted execution.

### 2. Agent Manifest - the contract

Agent Manifest is a proposed machine-readable file that introduces a website to AI agents. It is expected to live at:

```text
/.well-known/agent.json
```

It answers the questions an agent should ask before interacting with a site:

- Who are you?
- What do you offer?
- What knowledge can I trust?
- What capabilities can I call?
- Which actions are read-only?
- Which actions change state?
- Which actions require user consent?
- Which actions require human review?
- Which protocols should I use?
- How are results audited?


👉 [Agent Manifest Specification](https://github.com/intent-web/agent-manifest)

### 3. AgentLayer Framework - the implementation

AgentLayer Framework, or ALF, is the developer toolkit and runtime that can make existing websites IntentWeb-compatible.

It can generate manifests, expose capabilities, create LLM-readable files, export OpenAPI definitions, provide MCP tools, enforce consent policies and write audit logs.

👉 [AgentLayer Framework](https://github.com/intent-web/agent-layer-framework)

## How It Works

1. A user expresses an intent, for example: "Find alloy wheels that fit my car and prepare the cheapest safe offer."
2. An AI agent searches for websites that can satisfy that intent.
3. The agent checks whether a website exposes an Agent Manifest.
4. The agent reads identity, capabilities, policies, protocols and risk levels.
5. The agent selects a declared capability instead of guessing a browser path.
6. The agent gathers missing parameters or asks the user for details.
7. The agent requests explicit consent for medium, high or critical actions.
8. The agent executes through a governed endpoint.
9. The website returns a structured result and audit reference.

## Example: Buying Alloy Wheels

A user asks:

```text
Find the cheapest alloy wheels near me that fit my car and prepare an order.
```

A human understands that this requires more than a product search. The agent must consider vehicle model, wheel diameter, bolt pattern, width, offset, center bore, load rating, delivery, mounting, accessories, return policy and final approval.

An IntentWeb-ready store could expose capabilities such as:

- `search_wheels`
- `check_vehicle_fitment`
- `compare_total_price`
- `check_availability`
- `prepare_cart`
- `place_order`

The agent can safely call read-only capabilities, compare structured results and prepare a cart. But `place_order` is a critical transaction, so it must require explicit user confirmation and auditability.

## Capability Means More Than Endpoint

An endpoint tells an agent how to call something. A capability tells the agent what the action means.

| Endpoint | Capability |
| --- | --- |
| URL, method and payload | Intent, business meaning and constraints |
| Technical syntax | Technical syntax plus semantic context |
| Usually no risk model | Risk level, consent mode and audit rules |
| Often developer-facing | Agent-facing and policy-aware |

This distinction matters because agents need meaning and safety, not only API syntax.

## Risk And Consent Model

IntentWeb is built around explicit safety rules.

| Risk level | Meaning | Recommended behavior |
| --- | --- | --- |
| `low` | Public, read-only, non-sensitive data | May run without explicit confirmation |
| `medium` | Submits information or starts a workflow | Should ask for user confirmation |
| `high` | Modifies user data, creates bookings or changes configuration | Must ask for explicit confirmation |
| `critical` | Payments, orders, legal commitments or irreversible actions | Must require explicit approval, stronger authentication or human review, and audit |

Consent should be tied to the specific action, input, user and time. A vague "the agent may act for me" is not enough for sensitive operations.

## Adoption Paths

IntentWeb can be adopted gradually.

| Mode | What it does | Best for |
| --- | --- | --- |
| Static Mode | Publishes `agent.json`, `llms.txt`, catalogs and policies as files | Static websites, landing pages, documentation sites |
| Bridge Mode | Adds simple safe actions through PHP, serverless functions or existing APIs | Contact forms, offer requests, appointments |
| Runtime Mode | Adds policy enforcement, consent, authentication, OpenAPI, MCP and audit | E-commerce, SaaS, enterprise systems |

A website can become understandable to agents before it allows agents to perform actions.

## Technical Architecture

An IntentWeb-compatible implementation may include:

```text
AI Agent
  |
  | reads /.well-known/agent.json
  v
AgentLayer Runtime
  |
  |-- Manifest Generator
  |-- Capability Registry
  |-- Action Gateway
  |-- Policy Engine
  |-- Consent Engine
  |-- Trust and Audit Layer
  |-- Knowledge Catalog
  |-- Protocol Adapters
      |-- OpenAPI
      |-- MCP
      |-- Schema.org
      |-- llms.txt
  |
  v
Existing Website / CMS / E-commerce / CRM / SaaS / Business API
```

The important principle: **the runtime must enforce safety server-side.** Prompts alone are not a security model.

## Compatibility With Today's AI Ecosystem

IntentWeb is designed to work with existing web and AI standards instead of replacing them.

- **`/.well-known/`** for predictable discovery.
- **OpenAPI** for describing HTTP actions.
- **MCP** for exposing agent tools and resources.
- **Schema.org** for structured entities such as organizations, products, services and offers.
- **`llms.txt`** for LLM-readable website summaries.
- **Web App Manifest concepts** as inspiration for agent-facing metadata.

Current AI platforms can consume parts of this model through OpenAPI tools, MCP tools, custom connectors or browsing. Future agents could discover Agent Manifests directly.

## Business Value

For companies, IntentWeb is a path toward becoming agent-ready.

It can help businesses:

- Make offers, services, products and policies easier for AI assistants to understand.
- Reduce failed automation caused by fragile scraping or visual browsing.
- Turn websites into trusted capability providers.
- Improve discoverability in future AI-driven search and recommendation systems.
- Support safer lead generation, booking, quote requests and e-commerce workflows.
- Keep humans in control for sensitive actions.
- Create audit trails for agent-triggered operations.

In simple terms: **SEO made websites visible to search engines. IntentWeb can make websites useful to AI agents.**

## What IntentWeb Is Not

IntentWeb is not:

- A replacement for HTML, CSS, JavaScript or frontend frameworks.
- A replacement for OpenAPI, MCP, Schema.org or `llms.txt`.
- A chatbot widget.
- A permission system that lets agents bypass user consent.
- A guarantee that every AI agent will support the model immediately.
- An official registered web standard today.

IntentWeb should be understood as a proposed interoperability pattern and technical blueprint for the agentic web.

## Roadmap Direction

The first practical milestone is intentionally small:

1. Define Agent Manifest `v0.1`.
2. Publish JSON Schemas for manifests, capabilities and policies.
3. Provide examples for company sites, e-commerce, WordPress and SaaS.
4. Build validators so developers can check whether a site is IntentWeb-ready.
5. Generate static files for websites and Vue/Vite apps.
6. Create a WordPress plugin model for broad adoption.
7. Export OpenAPI definitions for safe actions.
8. Add MCP support for agent tool integration.
9. Introduce consent tokens, audit logs and trust metadata.
10. Prototype an IntentWeb index optimized for capabilities rather than pages.

## One-Sentence Definition

**IntentWeb is a web layer where websites are no longer only documents to view, but trusted capability contracts that AI agents can understand, evaluate and safely use.**

## Keywords

IntentWeb, Intent Web, AI-native web, agentic web, AI agents, autonomous agents, Agent Manifest, AgentLayer Framework, Agent Interface Optimization, AIO, machine-readable website, AI-ready website, agent-ready website, OpenAPI, MCP, llms.txt, Schema.org, web automation, safe AI actions, consent-based automation.

## Status

IntentWeb, Agent Manifest and AgentLayer Framework are currently presented as a proposed concept and implementation blueprint.

The detailed Agent Manifest specification and AgentLayer Framework implementation will be maintained in separate repositories:

- [Agent Manifest Specification](https://github.com/intent-web/agent-manifest)
- [AgentLayer Framework](https://github.com/intent-web/agent-layer-framework)
