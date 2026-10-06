<div align="center">

# Vafast

**High-performance, type-safe TypeScript web framework for Bun, Node.js & edge.**<br>
**超高性能、类型安全的 TypeScript Web 框架：结构清晰，显式可控。**

[![npm version](https://img.shields.io/npm/v/vafast?color=3178C6)](https://www.npmjs.com/package/vafast)
[![GitHub stars](https://img.shields.io/github/stars/vafast/vafast?style=flat)](https://github.com/vafast/vafast)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/vafast/vafast/blob/main/LICENSE)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0+-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)

[Docs (中文)](https://vafast.okayok.ai) · [Docs (English)](https://vafast.okayok.ai/en/) · [GitHub](https://github.com/vafast/vafast) · [npm](https://www.npmjs.com/package/vafast)

</div>

## Quick start · 快速开始

```bash
npx create-vafast-app
```

Or add it to an existing project · 或在现有项目中安装：

```bash
npm install vafast
```

```typescript
import { Server, defineRoute, defineRoutes, serve } from 'vafast';

const routes = defineRoutes([
  defineRoute({
    method: 'GET',
    path: '/',
    handler: () => 'Hello Vafast!'
  })
]);

const server = new Server(routes);
serve({ fetch: server.fetch, port: 3000 }, (info) => {
  console.log(`🚀 Server running at http://localhost:${info.port}`);
});
```

## Why Vafast · 特性

- ⚡ **Fast**: ~101K RPS, about 1.8× Express/Hono in our wrk benchmark (Bun 1.2). 性能约为 Express/Hono 的 1.8 倍。
- 🧭 **Declarative routes**: all routes in one array, no decorators or chain magic. 声明式路由数组，一眼看全。
- 🔒 **Type-safe end to end**: TypeBox schemas, JIT-compiled validators, types that survive across files. 类型跨文件不丢失。
- 🧩 **Explicit middleware**: declared on each route, with typed context injection. 中间件显式声明在路由上。
- 🧱 **Errors as data**: structured `VafastError` contracts. 错误即契约。
- 🗂️ **Route metadata**: custom fields + `RouteRegistry` for billing, permissions, webhooks, API specs. 声明式元数据。
- 🌍 **Runs anywhere**: Bun, Node.js and edge runtimes via the standard `fetch` handler. 一套代码，任意运行时。

## Ecosystem · 生态

Official plugins such as [CORS](https://github.com/vafast/vafast-cors), [Bearer](https://github.com/vafast/vafast-bearer) and [Compress](https://github.com/vafast/vafast-compress) live in this organization. Browse all [repositories](https://github.com/orgs/vafast/repositories).

---

<div align="center">

Built by [Okay OK](https://okayok.ai) · MIT License

</div>
