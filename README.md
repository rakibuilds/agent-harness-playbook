# Agent Harness Playbook

> A practitioner's guide to designing, choosing, and operating the runtime scaffolding around AI agents — the part everyone calls "the harness."

Most agent repos teach you how to *prompt* a model. This one is about everything else: the loop, the tools, the permissions, the memory, the cost, and the failure modes. **The harness is where agents succeed or fail in production** — and almost nobody writes down the decisions. This repo does.

---

## Why this repo exists

Agent harnesses are being reinvented every week. Teams ship a demo, hit production, and discover:

- The model was never the bottleneck — the **tool loop** was.
- Permissions were bolted on last, and now every new tool is a security review.
- Costs exploded because nobody measured **test-time compute vs. success rate**.
- A 100-line harness outperformed a 10,000-line framework for their use case — but they found out too late.

There is plenty of *code*. There is very little *judgment*. **This playbook is the decision layer**: trade-offs, selection matrices, anti-patterns, and migration paths — written for people who are about to build or replace a harness.

---

## What's inside

| Section | What you get | Read this if... |
|---|---|---|
| [`01-selection/`](./01-selection) | Decision matrix: minimal harness vs. framework vs. vendor SDK | You're choosing an architecture |
| [`02-architecture/`](./02-architecture) | Subsystem-by-subsystem breakdown (engine, tools, permissions, memory, hooks, MCP) | You're designing your own |
| [`03-permissions/`](./03-permissions) | Multi-tier permission models, path-level ACLs, human-in-the-loop approval | You're shipping to real users |
| [`04-cost-performance/`](./04-cost-performance) | Test-time compute vs. success rate, token break-even analysis | Your bill is growing |
| [`05-migration/`](./05-migration) | Moving from a hand-rolled loop to a framework (and back) | You've outgrown your harness |
| [`06-anti-patterns/`](./06-anti-patterns) | What we tried, what broke, and why | You want to avoid our mistakes |

Each section is **opinionated**, **short**, and ends with a **decision checklist** — not a link dump.

---

## Who this is for

- Engineers building an agent product who need to pick a harness **this quarter**
- Platform teams standardizing agent infrastructure across teams
- Anyone who has read the framework docs and still doesn't know **which trade-off to make**

**Not for you if** you want copy-paste code recipes — see [awesome-ai-agents](link) or a cookbook-style repo instead.

---

## How to use it

1. Start with [`01-selection/README.md`](./01-selection/README.md) — a 10-minute read that routes you to the right section.
2. Skim the **decision checklists** at the end of each doc.
3. Open an issue if your trade-off isn't covered — that's the most valuable contribution.

---

## Contributing

We want **field reports**, not links. If you've shipped a harness and hit a wall, write it up in `06-anti-patterns/`. See [CONTRIBUTING.md](./CONTRIBUTING.md).

## License

[MIT](./LICENSE)
