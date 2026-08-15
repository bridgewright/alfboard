# Interview-to-Report Handoff Contract

The interview skill owns `deployment-discovery.json`. The report skill may consume the record only after deterministic validation succeeds.

Required behavior:

1. Preserve transcript evidence and the participant role.
2. Use controlled values defined in `discovery-spec.md`.
3. Represent unavailable evidence as `unknown` or in `open_questions`.
4. Do not write deployment or product documents when validation returns an error.
5. Treat warnings as explicit review items in the resulting documents.

The report skill must not modify the discovery record to make writing easier. Additional evidence requires another interview or a documented user correction.
