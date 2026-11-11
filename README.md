# Agent Harness Playbook

A practitioner's guide to the runtime layer around AI agents — the loop, the tools, the permissions, the memory, the cost. The part that decides whether an agent works in production or only in a demo.

---

## What this is

Every agent has a harness: the code that runs the model in a loop, gives it tools, gates its actions, and decides when to stop. This repo is a collection of **decisions, trade-offs, and field notes** about building that layer well.

It is not a framework. It is not a tutorial. It is the thinking you do *before* and *while* you build one.

---

## Why it exists

Most agent failures are not model failures. They are harness failures:

- The tool loop retries forever or gives up too early.
- Permissions are added after launch, so every new tool becomes a security review.
- Nobody measured cost per successful task until the bill arrived.
- A small, well-designed harness outperformed a large framework — but the team found out months in.

These lessons are learned repeatedly and written down rarely. This repo writes them down.

---

## What's inside

| Folder | Contents |
|---|---|
| [`01-selection/`](./01-selection/README.md) | How to choose between a minimal harness, a framework, and a vendor SDK — with a decision matrix |
| [`02-architecture/`](./02-architecture/README.md) | Subsystem breakdown: engine, tools, permissions, memory, hooks, MCP |
| [`03-permissions/`](./03-permissions/README.md) | Permission tiers, path-level access control, human-in-the-loop approval |
| [`04-cost-performance/`](./04-cost-performance/README.md) | Test-time compute vs. success rate, token cost break-even |
| [`05-migration/`](./05-migration/README.md) | Moving between hand-rolled loops and frameworks, in both directions |
| [`06-anti-patterns/`](./06-anti-patterns/README.md) | Approaches that failed, and why |

Each document is short, opinionated, and ends with a **decision checklist** you can act on.

---

## Start here

New to the repo? Read these in order:

1. [Selection: choosing a harness](./01-selection/README.md) — the decision matrix that routes you to the rest.
2. [Architecture: the six subsystems](./02-architecture/README.md) — what a harness is actually made of.
3. [Anti-patterns: what broke](./06-anti-patterns/README.md) — read this before you build, not after.

---

## Who it's for

- Engineers choosing a harness architecture for a product shipping this quarter
- Platform teams standardizing agent infrastructure across teams
- Anyone who has read the framework docs and still doesn't know which trade-off to make

---

## How to use it

1. Open [Selection](./01-selection/README.md) — a short read that points you to the right section for your situation.
2. Skim the decision checklist at the end of each document.
3. If your situation isn't covered, open an issue. Field reports are the most valuable contribution.

---

## Contributing

Contributions should be **field reports and trade-off analyses**, not link collections. If you've shipped a harness and hit a wall, write it up in [`06-anti-patterns/`](./06-anti-patterns/README.md). See [`CONTRIBUTING.md`](./CONTRIBUTING.md).

## License

[MIT](./LICENSE)
