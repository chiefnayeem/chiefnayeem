# Mohammed Nayeem
### Senior Full-Stack Engineer · 9+ years

I build production systems across the whole request path — NestJS and Node services over PostgreSQL and Redis, React and Next.js on top, React Native where a product needs an app. Most of my recent work has been on systems with real constraints: caches that must stay correct under concurrent writes, scheduled jobs that must be safe to run twice, and repositories several people change at once.

📍 Bangladesh (UTC+6) · 🌐 [mohammed-nayeem.vercel.app](https://mohammed-nayeem.vercel.app) · Open to full-time remote roles

---

## Open source

### [redis-graph-cache](https://www.npmjs.com/package/redis-graph-cache)

[![npm](https://img.shields.io/npm/v/redis-graph-cache?color=CB3837&label=npm)](https://www.npmjs.com/package/redis-graph-cache)
[![license](https://img.shields.io/npm/l/redis-graph-cache?color=10b981)](https://github.com/chiefnayeem/redis-graph-cache/blob/main/LICENSE)
[![docs](https://img.shields.io/badge/docs-redis--graph--cache.vercel.app-10b981)](https://redis-graph-cache.vercel.app)

A schema-driven Redis data layer for Node.js. Entities, lists and sorted-set indexes are declared once — fields, types, relations, TTLs — and the library normalises on write and hydrates the object graph on read, so a cached list returns its related records without the caller fanning out the reads itself.

~5,400 lines of TypeScript, zero runtime dependencies (`ioredis` as a peer).

- **Atomicity pushed into Lua.** Multi-key work — appending to a list and its index together, cascading an invalidation across every list a deleted entity appears in — runs as one of 7 Lua scripts inside Redis, so no other client observes a half-updated cache.
- **Fails closed rather than degrading quietly.** Circuit breaker with a half-open probe and exponential backoff. Serialization errors deliberately bypass the fallback path, because a fallback that swallows a corrupt payload turns a loud failure into a silent wrong answer.
- **`null` and `undefined` mean different things.** Writes smart-merge: an omitted field is preserved, an explicit `null` clears it, arrays replace wholesale. Specified in the docs rather than left to be discovered in production.

---

## Shipped

### MyGouripur — [Google Play](https://play.google.com/store/apps/details?id=com.mygouripur) · [mygouripur.com](https://mygouripur.com)

A local commerce platform for a town in Bangladesh — merchant pages with products, food menus, services and doctors' chamber hours, plus a community feed and classifieds. Four codebases, all mine: NestJS API, React Native app, public site, admin console.

- Registers **197 cache schemas** against `redis-graph-cache` — 125 entities and 72 sorted-set indexes — under the invariant that an entity must outlive by 2× any list referencing it.
- Feed lists are warm windows rebuilt single-flight under a lock, so a miss does not send a thundering herd at Postgres. Deep feeds paginate by keyset cursor: page 1,000 costs what page 1 costs.
- Every read degrades to Postgres on a Redis fault. An outage slows the app down; it does not take it down.
- Notification crons take transaction-scoped Postgres advisory locks, with a per-recipient-per-day unique index as the real backstop.
- Merchant broadcast copy is written by an LLM and then validated against the source data. Doctor chamber-hour reminders deliberately are not — a paraphrased clinic time sends someone to a closed door, so a fixed Bangla template is correct by construction.

---

## Stack

**Frontend** — React, Next.js, TypeScript, Vue.js, Tailwind CSS, Redux Toolkit
**Mobile** — React Native, Reanimated, push notifications, offline caching
**Backend** — Node.js, NestJS, Express, Laravel, REST, GraphQL, WebSockets
**Data** — PostgreSQL, MySQL, MongoDB, Redis, Prisma, TypeORM, Knex
**Infrastructure** — Docker, GitHub Actions, AWS, Cloudflare R2, Nginx, CI/CD
**Applied AI** — LLM integration, structured prompting, output validation, LangChain, MCP servers

---

## Contact

Open to full-time remote roles on a product team I can stay with long term.

**chiefnayeem@gmail.com** · [LinkedIn](https://linkedin.com/in/md-nayeem-bhuiyan)
