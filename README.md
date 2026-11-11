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
| `01-selection/` | How to choose between a minimal harness, a framework, and a vendor SDK — with a decision matrix |
| `02-architecture/` | Subsystem breakdown: engine, tools, permissions, memory, hooks, MCP |
| `03-permissions/` | Permission tiers, path-level access control, human-in-the-loop approval |
| `04-cost-performance/` | Test-time compute vs. success rate, token cost break-even |
| `05-migration/` | Moving between hand-rolled loops and frameworks, in both directions |
| `06-anti-patterns/` | Approaches that failed, and why |

Each document is short, opinionated, and ends with a **decision checklist** you can act on.

---

## Who it's for

- Engineers choosing a harness architecture for a product shipping this quarter
- Platform teams standardizing agent infrastructure across teams
- Anyone who has read the framework docs and still doesn't know which trade-off to make

---

## How to use it

1. Open `01-selection/README.md` — a short read that points you to the right section for your situation.
2. Skim the decision checklist at the end of each document.
3. If your situation isn't covered, open an issue. Field reports are the most valuable contribution.

---

## Contributing

Contributions should be **field reports and trade-off analyses**, not link collections. If you've shipped a harness and hit a wall, write it up in `06-anti-patterns/`. See `CONTRIBUTING.md`.

## License

MIT
