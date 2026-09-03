# Mohammed Nayeem
### Senior Full-Stack Engineer · 9+ years

I build production systems across the whole request path — services and data on one end, web and mobile on the other. Nine years of it, most of it multi-tenant SaaS and commerce platforms that live in private client repositories.

Two pieces are public: [`redis-graph-cache`](https://www.npmjs.com/package/redis-graph-cache) on npm, and [My Gouripur](https://play.google.com/store/apps/details?id=com.mygouripur) on Google Play.

📍 Bangladesh (UTC+6) · 🌐 [mohammed-nayeem.vercel.app](https://mohammed-nayeem.vercel.app) · Open to full-time remote roles

---

## Core stack

The things I use daily and would happily be questioned on in depth.

| | | |
| :--: | :-- | :-- |
| <img src="https://cdn.simpleicons.org/typescript/3178C6" width="17" align="top" /> | **TypeScript** | Strict mode across every project. Typed API contracts end to end, so a broken shape fails the build instead of production. |
| <img src="https://cdn.simpleicons.org/react/61DAFB" width="17" align="top" /> <img src="https://cdn.simpleicons.org/nextdotjs/888888" width="17" align="top" /> | **React · Next.js** | App Router, custom Webpack plugin setups, and micro-frontend embedding — one bundle mounted into Vue and Laravel Blade hosts. |
| <img src="https://cdn.simpleicons.org/react/61DAFB" width="17" align="top" /> | **React Native** | CLI rather than Expo. Animation on the UI thread, list virtualisation, offline-tolerant caching, store releases. |
| <img src="https://cdn.simpleicons.org/nodedotjs/5FA04E" width="17" align="top" /> <img src="https://cdn.simpleicons.org/nestjs/E0234E" width="17" align="top" /> | **Node.js · NestJS** | REST and GraphQL. Thin controllers, services owning the logic, repositories owning data access, Swagger-documented. |
| <img src="https://cdn.simpleicons.org/laravel/FF2D20" width="17" align="top" /> <img src="https://cdn.simpleicons.org/php/8892BF" width="17" align="top" /> | **Laravel · PHP** | Four years leading an eCommerce build on it, and several since. Lately modernising Blade apps in place — React mounted into existing views rather than a rewrite. |
| <img src="https://cdn.simpleicons.org/postgresql/4169E1" width="17" align="top" /> | **PostgreSQL** | Keyset pagination, transaction-scoped advisory locks, polymorphic modelling that extends without migrations. Knex, Prisma and TypeORM depending on the project. |
| <img src="https://cdn.simpleicons.org/redis/FF4438" width="17" align="top" /> | **Redis** | Deep enough to have written a library for it — schema-driven normalization, Lua atomicity, circuit breaking. |
| <img src="https://cdn.simpleicons.org/graphql/E10098" width="17" align="top" /> | **GraphQL · WebSockets** | Apollo, plus the reconnection and state-reconciliation paths that decide whether real-time is usable. |

## Also work with

| | |
| :-- | :-- |
| **Frontend** | <img src="https://cdn.simpleicons.org/vuedotjs/4FC08D" width="15" align="top" /> Vue.js &nbsp; <img src="https://cdn.simpleicons.org/nuxt/00DC82" width="15" align="top" /> Nuxt &nbsp; <img src="https://cdn.simpleicons.org/tailwindcss/06B6D4" width="15" align="top" /> Tailwind CSS &nbsp; <img src="https://cdn.simpleicons.org/redux/764ABC" width="15" align="top" /> Redux Toolkit &nbsp; <img src="https://cdn.simpleicons.org/reactquery/FF4154" width="15" align="top" /> TanStack Query &nbsp; Zustand |
| **Data** | <img src="https://cdn.simpleicons.org/prisma/9AA4B2" width="15" align="top" /> Prisma &nbsp; <img src="https://cdn.simpleicons.org/typeorm/FE0803" width="15" align="top" /> TypeORM &nbsp; <img src="https://cdn.simpleicons.org/knexdotjs/D26B38" width="15" align="top" /> Knex &nbsp; Objection &nbsp; <img src="https://cdn.simpleicons.org/mysql/4479A1" width="15" align="top" /> MySQL &nbsp; <img src="https://cdn.simpleicons.org/mongodb/47A248" width="15" align="top" /> MongoDB |
| **Infra** | <img src="https://cdn.simpleicons.org/docker/2496ED" width="15" align="top" /> Docker &nbsp; <img src="https://cdn.simpleicons.org/githubactions/2088FF" width="15" align="top" /> GitHub Actions &nbsp; AWS Lambda &nbsp; <img src="https://cdn.simpleicons.org/cloudflare/F38020" width="15" align="top" /> Cloudflare R2 &nbsp; <img src="https://cdn.simpleicons.org/firebase/FFCA28" width="15" align="top" /> Firebase |
| **Also** | <img src="https://cdn.simpleicons.org/express/9AA4B2" width="15" align="top" /> Express &nbsp; <img src="https://cdn.simpleicons.org/electron/47848F" width="15" align="top" /> Electron &nbsp; <img src="https://cdn.simpleicons.org/gatsby/663399" width="15" align="top" /> Gatsby &nbsp; <img src="https://cdn.simpleicons.org/stripe/635BFF" width="15" align="top" /> Stripe &nbsp; <img src="https://cdn.simpleicons.org/langchain/9AA4B2" width="15" align="top" /> LangChain &nbsp; MCP servers |

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

**[My Gouripur](https://play.google.com/store/apps/details?id=com.mygouripur)** — a local commerce platform for a town in Bangladesh. Four codebases, all mine: NestJS API, React Native app, public site, admin console. Runs on `redis-graph-cache` in production across 197 cache schemas.

Live on [Google Play](https://play.google.com/store/apps/details?id=com.mygouripur) and [mygouripur.com](https://mygouripur.com). Source is private; the engineering write-up is on [my site](https://mohammed-nayeem.vercel.app).

**Delivered under contract**, source not mine to publish: a multi-tenant WhatsApp automation SaaS with Stripe billing and RBAC; a multi-tenant e-commerce platform with per-merchant subdomains; an embeddable chat product loaded into a customer's Vue app; a Laravel field-operations platform modernised in place with React widgets and a Node WebSocket service. Written up on [my site](https://mohammed-nayeem.vercel.app).

---

## Contact

Open to full-time remote roles on a product team I can stay with long term.

**chiefnayeem@gmail.com** · [LinkedIn](https://linkedin.com/in/md-nayeem-bhuiyan)
