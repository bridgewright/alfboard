# Alfboard

**A voice-led discovery workflow for planning enterprise AI deployments and returning field evidence to the product team.**

Alfboard interviews four stakeholder groups, validates the resulting discovery record, and produces two review-ready documents: an executive deployment brief and a product input document. It addresses deployment preparation and product feedback; it does not deploy an AI agent or connect production systems.

The project was originally designed as a public-information case study around the deployment of Channel Corporation's AI agent. It is an independent portfolio project and is not affiliated with or endorsed by Channel Corporation or ElevenLabs.

## Problem Definition

Enterprise AI deployment work often repeats the same discovery effort for every customer. Deployment teams must reconstruct workflows, system constraints, knowledge readiness, change-management needs, and success measures. At the same time, the evidence collected in the field is frequently summarized too loosely to inform the product roadmap.

Alfboard creates one explicit handoff contract between discovery and writing. The interview collects concrete examples and unknowns; deterministic validation decides whether the record is complete enough to use; the reporting skill turns the validated record into documents for two different audiences.

## Workflow

```text
CS leader ─┐
Executive ─┼── browser-based voice interviews
Agent ─────┤                 │
IT lead ───┘                 ▼
                    deployment-discovery.json
                              │
                       deterministic validation
                              │
                   ┌──────────┴──────────┐
                   ▼                     ▼
        executive deployment       product input
                brief                 document
```

The interviewer targets evidence slots rather than reciting a fixed questionnaire. It asks for a recent event, frequency, operational consequence, current workaround, system dependency, and measurable desired result. Missing information remains `unknown` or is added to `open_questions`. Reporting stops when the discovery contract is invalid.

## Installation

```bash
git clone https://github.com/bridgewright/alfboard.git
cd alfboard
```

For Codex:

```bash
codex plugin marketplace add bridgewright/alfboard
codex plugin add alfboard@alfboard
```

For Claude Code:

```bash
claude plugin marketplace add bridgewright/alfboard
claude plugin install alfboard@alfboard
```

The live interview requires an ElevenLabs API key. Copy the example environment file, install the pinned dependencies, configure the agent, and launch the local interview page:

```bash
cp skills/interview/.env.example skills/interview/.env
bash skills/interview/setup.sh
bash skills/interview/launch.sh
```

Secrets remain local and must never be committed.

## Commands

- `/alfboard:interview` conducts stakeholder discovery and produces `deployment-discovery.json`.
- `/alfboard:report` consumes a valid discovery record and produces `deployment-brief.md` and `product-input.md`.

## Evaluation

```bash
python3 skills/interview/scripts/validate_discovery.py \
  skills/interview/assets/sample-discovery.json
python3 -m pytest skills/interview/tests -q
```

The automated tests cover required fields, controlled values, empty collections, unknown information, and invalid-contract refusal. The repository also contains a complete fictional example built from nine interviews across four stakeholder groups. The launch path was reduced from 27 tool calls to two, with an observed cold start of approximately two seconds in the original development environment.

## Limitations

- The complete example is fictional; the workflow has not been calibrated with production customer data.
- The two documents are drafted by an agent and require professional review.
- Cost and benefit calculations depend on explicit assumptions and customer-provided evidence.
- Voice setup requires a third-party API and has not been automated in continuous integration.
- The system prepares a deployment decision; it does not execute the deployment.

## Licensing and Third-Party Material

Original software is licensed under the MIT License. Company names, product names, trademarks, third-party APIs, and externally published source material are excluded. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
