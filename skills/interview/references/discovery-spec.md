# Deployment Discovery Contract

`deployment-discovery.json` is the single handoff between voice discovery and report generation. `scripts/validate_discovery.py` enforces the controlled values and required structure. Change this specification, the validator, the sample, and downstream instructions together.

## Evidence model

The contract organizes evidence across three dimensions:

- **Work and bottlenecks:** context, repeated events, automation scope, and organizational change
- **Systems and integration:** application ownership, interfaces, security constraints, and knowledge readiness
- **Performance and impact:** baseline measures, target measures, assumptions, and unresolved questions

The interviewer is goal-directed rather than questionnaire-driven. A field must not be populated unless the transcript supports it.

## Top-level structure

```jsonc
{
  "meta": {
    "customer": "Fictional customer",
    "interviewee_role": "cs_lead",
    "interviewees": [{"role": "cs_lead", "who": "Customer service lead"}],
    "company_size": "enterprise",
    "created_at": "2026-07-06",
    "created_by": "voice interview",
    "source_transcript": "output/transcript.jsonl"
  },
  "context": {},
  "bottlenecks": [],
  "automation_scope": [],
  "integration": {},
  "knowledge_readiness": {},
  "org_change": {},
  "metrics": {},
  "product_gaps": [],
  "open_questions": []
}
```

## Controlled values

- `meta.interviewee_role`: `cs_lead`, `exec`, `agent`, `it`, or `multi`
- `meta.company_size`: `smb` or `enterprise`
- Integration tier: `no_integration`, `workflow`, or `system_task`
- Product-gap tags: `action_task`, `reask_context`, `knowledge_authoring`, `voc_distribution`, `metric_redefine`, `handoff_quality`, `multilingual`, or `small_team`

The committed sample is the executable field-level reference. Validate it after every contract change:

```bash
python3 skills/interview/scripts/validate_discovery.py \
  skills/interview/assets/sample-discovery.json
```

## Quality rules

- Prefer exact counts, times, owners, and recent events over adjectives.
- Preserve the difference between an observed fact, an interviewee estimate, and a project assumption.
- Do not convert `unknown` into zero, false, or an empty collection when the distinction is material.
- Record integration ownership, interface availability, documentation quality, security requirements, and internal engineering capacity separately.
- Define success as a balanced set of operational and customer outcomes rather than a single automation rate.
- Put missing decision evidence in `open_questions` and carry it into both reports.
