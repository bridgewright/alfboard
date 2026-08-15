---
description: Produce an executive deployment brief and a product input document from a validated discovery record.
allowed-tools: [Bash, Read, Write, AskUserQuestion]
---

Use `skills/report/SKILL.md`.

If no usable `deployment-discovery.json` exists, do not invent one. Ask whether the user wants to inspect the fictional MoveOn example in `samples/moveon/`, provide a discovery path, or conduct an interview first.

For a real discovery record:

1. Validate it with `skills/interview/scripts/validate_discovery.py`.
2. Follow `skills/report/references/deployment-brief-format.md` and `costing-assumptions.md` to write `deployment-brief.md`.
3. Follow `skills/report/references/product-input-format.md` to write `product-input.md`.
4. Mark unavailable evidence as requiring confirmation. Do not convert an assumption into a fact.

Honor any discovery path supplied in `$ARGUMENTS`.
