# Curriculum template: ground zero -> junior developer

This is the master template, NOT a user's curriculum. During setup (see `setup.md`), copy it to `~/.claude/sensei/curriculum.md`, then prune and reorder it to the user's goals and stack. Never edit this file for one user.
Pruning rules: drop topics outside the user's stack; if a dropped topic is a prerequisite of a kept one, drop that dependency too (or keep the topic); renumbering is not needed, ids are stable.

Rules: ordered. One topic = one feature-sized lesson. Move on when the topic is `solid`. Never teach a topic whose prerequisites are below `shaky`. Topics marked (concept) may use a worked-example format instead of code.
Format: id | topic | needs

## A. Foundations
01 | How computers run code (CPU, memory, files, processes) | -
02 | Terminal and shell (paths, commands, env vars, PATH) | 01
03 | Git and GitHub (commit, branch, merge, remote, pull request, undo) | 02
04 | Variables, types, operators | 01
05 | Control flow (if, loops) | 04
06 | Functions and scope | 05
07 | Debugging (reading errors, logging, debugger, isolating bugs) | 06

## B. Core programming
08 | Data structures (arrays, objects/dicts, sets, stacks, queues) | 06
09 | Strings, files, JSON, and I/O | 06
10 | Recursion and basic algorithms (search, sort, Big-O intuition) | 08
11 | Error handling and exceptions | 07
12 | Modules, packages, npm/pip, dependencies and lockfiles | 09
13 | Object-oriented basics and composition | 08
14 | Testing (unit, integration, mocks, test design) | 11

## C. Languages
15 | Python basics and idioms | 08, 09
16 | JavaScript core (scope, closures, `this`, prototypes, equality) | 06, 08
17 | Async JavaScript (callbacks, promises, async/await, event loop) | 16
18 | TypeScript (types, interfaces, generics, narrowing, config) | 16

## D. Web frontend
19 | HTTP and how the web works (requests, status codes, headers, cookies, CORS) | 09
20 | HTML and semantic markup, accessibility basics | 19
21 | CSS (box model, flexbox, grid, responsive design) | 20
22 | The DOM and browser events | 16, 21
23 | Tailwind CSS (utility-first, design tokens, responsive variants) | 21
24 | React core (components, props, state, effects, hooks, rendering) | 18, 22
25 | State management (Zustand, Redux, when local vs global state) | 24
26 | Next.js (routing, SSR/SSG/CSR, API routes, data fetching) | 24

## E. Backend and data
27 | Node.js runtime (modules, event loop, streams, env config) | 17
28 | Express and REST API design (routes, middleware, status codes, validation) | 27, 19
29 | MVC and project structure (separation of concerns, clean architecture) | 28, 13
30 | Authentication and authorization (hashing, sessions, JWT, OAuth idea) | 28
31 | Security basics (injection, XSS, CSRF, secrets, OWASP top 10) | 30
32 | SQL and PostgreSQL (tables, queries, joins, indexes, transactions, modeling) | 08
33 | MongoDB and NoSQL (documents, schema design, SQL vs NoSQL tradeoffs) | 32
34 | Redis and caching (key-value, TTL, cache invalidation, sessions, pub/sub) | 32
35 | WebSockets and Socket.io (rooms, events, reconnects, scaling issues) | 28, 17
36 | Event-driven architecture (queues, pub/sub, eventual consistency) | 34, 35

## F. Mobile
37 | React Native (components, navigation, native vs web differences, Expo basics) | 24
38 | Mobile concerns (offline, push notifications, permissions, app lifecycle) | 37

## G. Cloud and operations
39 | Docker (images, containers, volumes, compose) | 02, 27
40 | Object storage and cloud basics (S3, Cloudflare R2, Google Cloud, IAM, signed URLs) | 28
41 | Deployment, CI/CD, environments, config and logging | 39, 03
42 | Performance and reliability (latency, uptime, how they are measured, monitoring) | 41

## H. Product and extensions
43 | Chrome extensions (manifest v3, content/background scripts, messaging, Webpack and bundling) | 24
44 | Using LLM APIs (Gemini/OpenAI, prompts, tokens, rate limits, API-key safety, comparing model outputs, confidence scoring) | 28
45 | Shopify and e-commerce (themes/Liquid, Storefront/Admin API, integrating external APIs) (concept+code) | 28
46 | Agile, Jira and Confluence, working in a team (concept) | -
47 | UX/UI basics and user flows (Figma, wireframes, usability) (concept) | -

## I. Professional practice
48 | Reading and reviewing unfamiliar code | 14
49 | Code quality (naming, structure, refactoring, DRY vs clarity) | 29
50 | System design basics (requirements, components, tradeoffs, scaling a simple app) | 36, 42
51 | Working with AI coding tools responsibly (verify output, prompting, avoid blind trust) | 07
52 | Explaining your work (project walkthroughs, technical interview basics) (concept) | 50

Default milestone for "junior developer" (adjust to the pruned list): topics 01-14, 16-18, 19-26, 27-34 and 41 are `solid`; the rest at least `shaky`.
