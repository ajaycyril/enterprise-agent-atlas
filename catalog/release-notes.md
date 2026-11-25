---
layout: default
title: "Release landmarks"
permalink: /catalog/release-notes.html
parent: "Library catalog"
---

# Releases that change a build prompt

Research cutoff · 25 November 2026. Dates below are vendor publication dates. These are release landmarks. Resolve current security patches, runtime and peer dependencies together before locking a production build.

| Published | Verified upstream change | What to change in your brief |
|---|---|---|
| 17 Nov 2026 | eve 1.0 reached general availability. Its harness calls models and tools, delegates to subagents and persists progress through Workflow SDK. | For a Vercel-first team, evaluate one integrated harness before assembling separate orchestration, approval and durability packages. Run your own crash, export and retention tests. [Release](https://vercel.com/blog/eve-is-now-generally-available) |
| 16 Nov 2026 | React Flow 13 added per-node and per-edge subscription hooks, split its stores and introduced breaking changes to connection and store APIs. | Ask for v13-compatible examples and narrow subscriptions on the live canvas. Review the migration guide before reusing a v12 graph snippet. [Release](https://reactflow.dev/whats-new/2026-11-16) |
| 6 Nov 2026 | Vercel Tracing reached GA. Its announcement describes automatic instrumentation for eligible new Next.js 16.5 projects with a Node.js function. | Decide how framework spans correlate with business runs. Specify a separate retention policy for audit records. [Release and eligibility](https://vercel.com/changelog/vercel-tracing-is-now-generally-available) |
| 9 Sep 2026 | React 19.3 includes View Transitions. | Use a navigation transition for moving between screens. Specify Motion for event-driven states within the run, and assign each animated property one owner. [React release](https://react.dev/blog/2026/09/09/react-19-3) |
| 28 Jul 2026 | MCP published the 2026-07-28 specification, including a stateless protocol core and authorization changes. | Pin client and server protocol support. Verify your tool grants and negotiation with the actual server. [Protocol release](https://blog.modelcontextprotocol.io/posts/2026-07-28/) |
| Jul 2026 | shadcn/ui changed its default foundation for new projects to Base UI. Radix remains supported. | Name the primitive family. For an existing Radix product, keep its established composition conventions. [Changelog](https://ui.shadcn.com/docs/changelog/2026-07-base-ui-default) |
| 25 Jun 2026 | Vercel released AI SDK 7. | Use examples from the matching SDK major and test the actual provider adapter and stream format. [Release](https://vercel.com/blog/ai-sdk-7) |
| 3 Apr 2026 | Microsoft Agent Framework 1.0 shipped for .NET and Python. Microsoft publishes migration paths from AutoGen and Semantic Kernel. | For a Microsoft estate, assess the supported successor and test the specific connector before copying an older tutorial. [Release](https://devblogs.microsoft.com/agent-framework/microsoft-agent-framework-version-1-0/) · [Migration](https://learn.microsoft.com/en-us/agent-framework/migration-guide/) |

The Next.js support page inspected for this edition lists 16.x as Active LTS and 15.x in maintenance. Pick a supported patched line and use its documented React pairing. An exact patch belongs in the application's lockfile. [Support policy](https://nextjs.org/support-policy)

## How to refresh an entry

1. Start with the official link in `tools.json`. Open the release and support or security policy for the edition you intend to ship.
2. Record the last stable release you actually verified, breaking migrations, runtime requirements and any feature-specific paid terms. A GA label for a product can coexist with preview APIs.
3. In a branch, exercise one representative workflow with the new version. Check trace compatibility, keyboard access, retry behavior, data export and cost. Record results with a date, workload and owner.
4. Update the source, tradeoff and prompt fragment in the relevant catalog page and in `tools.json`.
