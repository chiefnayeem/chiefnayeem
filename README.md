# Mohammed Nayeem
### Senior Full-Stack Engineer · 9+ years

I build production systems across the whole request path — services and data on one end, web and mobile on the other. I wrote and maintain [`redis-graph-cache`](https://www.npmjs.com/package/redis-graph-cache) on npm, and [MyGouripur](https://play.google.com/store/apps/details?id=com.mygouripur) on Google Play.

📍 Bangladesh (UTC+6) · 🌐 [mohammed-nayeem.vercel.app](https://mohammed-nayeem.vercel.app) · Open to full-time remote roles

---

## Core stack

The things I use daily and would happily be questioned on in depth.

| | |
| :-- | :-- |
| **TypeScript** | Strict mode across every project. Typed API contracts end to end, so a broken shape fails the build instead of production. |
| **React · Next.js** | App Router, custom Webpack plugin setups, and micro-frontend embedding — one bundle mounted into Vue and Laravel Blade hosts. |
| **React Native** | CLI rather than Expo. Animation on the UI thread, list virtualisation, offline-tolerant caching, store releases. |
| **Node.js · NestJS** | REST and GraphQL. Thin controllers, services owning the logic, repositories owning data access, Swagger-documented. |
| **PostgreSQL** | Keyset pagination, transaction-scoped advisory locks, polymorphic modelling that extends without migrations, Knex. |
| **Redis** | Deep enough to have written a library for it — schema-driven normalization, Lua atomicity, circuit breaking. |
| **GraphQL · WebSockets** | Apollo, plus the reconnection and state-reconciliation paths that decide whether real-time is usable. |

## Also work with

Vue.js · Nuxt · Laravel · PHP · Express · Redux Toolkit · Zustand · TanStack Query · Tailwind CSS · NativeWind · Prisma · TypeORM · Objection · Knex · MySQL · MongoDB · Docker · GitHub Actions · AWS Lambda · Cloudflare R2 · Firebase · Electron · Gatsby · Stripe · LangChain · MCP servers

---

## Open source

### [redis-graph-cache](https://www.npmjs.com/package/redis-graph-cache)

[![npm](https://img.shields.io/npm/v/redis-graph-cache?color=CB3837&label=npm)](https://www.npmjs.com/package/redis-graph-cache)
[![license](https://img.shields.io/npm/l/redis-graph-cache?color=10b981)](https://github.com/chiefnayeem/redis-graph-cache/blob/main/LICENSE)
[![docs](https://img.shields.io/badge/docs-redis--graph--cache.vercel.app-10b981)](https://redis-graph-cache.vercel.app)

A schema-driven Redis data layer for Node.js. Entities, lists and sorted-set indexes are declared once — fields, types, relations, TTLs — and the library normalises on write and hydrates the object graph on read, so a cached list returns its related records without the caller fanning out the reads. ~5,400 lines of TypeScript, zero runtime dependencies.

- **Atomicity pushed into Lua.** Multi-key work runs as one of 7 scripts inside Redis, so no client observes a half-updated cache.
- **Fails closed rather than degrading quietly.** Circuit breaker with a half-open probe. Serialization errors bypass the fallback, because a fallback that swallows a corrupt payload turns a loud failure into a silent wrong answer.
- **`null` and `undefined` mean different things.** Omitted fields are preserved, explicit `null` clears, arrays replace wholesale — specified in the docs rather than discovered in production.

---

## Shipped

**[MyGouripur](https://play.google.com/store/apps/details?id=com.mygouripur)** — a local commerce platform for a town in Bangladesh. Four codebases, all mine: NestJS API, React Native app, public site, admin console. Runs on `redis-graph-cache` in production across 197 cache schemas.

Live on [Google Play](https://play.google.com/store/apps/details?id=com.mygouripur) and [mygouripur.com](https://mygouripur.com). Source is private; the engineering write-up is on [my site](https://mohammed-nayeem.vercel.app).

---

## Contact

Open to full-time remote roles on a product team I can stay with long term.

**chiefnayeem@gmail.com** · [LinkedIn](https://linkedin.com/in/md-nayeem-bhuiyan)
