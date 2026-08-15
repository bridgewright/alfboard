# Fictional End-to-End Example

The `moveon/` directory represents a fictional Korean fashion-commerce company. It demonstrates how evidence from nine interviews across four stakeholder groups becomes one discovery contract and two decision documents.

```text
moveon/
  transcripts/
    cs_lead.md
    exec.md
    agent.md
    it.md
  deployment-discovery.json
  deployment-brief.md
  product-input.md
```

The transcripts and generated documents remain in Korean because they demonstrate the native-language operating workflow. All people, company details, events, volumes, systems, and quotations are fictional.

The example illustrates four principles:

1. Each stakeholder group contributes different evidence: operating baseline, executive priorities, frontline edge cases, and technical constraints.
2. The executive deployment brief and product input document use the same evidence but serve different decisions.
3. Cost estimates expose assumptions and effort rather than presenting an unexplained total.
4. Missing evidence remains under `open_questions` and is never invented for narrative completeness.

Validate the discovery contract with:

```bash
python3 skills/interview/scripts/validate_discovery.py \
  samples/moveon/deployment-discovery.json
```
