---
name: interview
description: Use this skill to conduct a Korean voice interview with a customer-service leader, executive, frontline agent, or information-technology stakeholder before an enterprise AI deployment. It captures concrete operational evidence and produces a validated deployment-discovery.json contract for the report skill.
version: 1.0.0
permissions:
  - file_read
  - file_write
  - env
  - network
---

# Voice-Led Deployment Discovery

Launch the local browser interview immediately:

```bash
bash skills/interview/launch.sh
```

The script manages the virtual environment, ElevenLabs agent, local server, and browser URL. The interviewer begins by identifying the participant's role and then follows the appropriate evidence path. The live conversation is in Korean because the original deployment case study targets Korean operating teams.

After the interview:

1. Fetch the turn-level transcript with `scripts/fetch_transcript.py`.
2. Populate `output/deployment-discovery.json` according to `references/discovery-spec.md`.
3. Use concrete events, frequency, workflow, system, organizational, and measurement evidence from the transcript.
4. Preserve unsupported slots as `unknown` or under `open_questions`.
5. Run `scripts/validate_discovery.py`; return to discovery if validation fails.

## Guardrails

- Ask one question at a time and use a recent event before requesting an abstract judgment.
- Do not fill a slot without interview evidence.
- Keep real transcripts, environment files, and generated output outside Git.
- Treat `prompt/interviewer-system-prompt.md` as the single source for interviewer behavior.
- Do not expose an API key, agent identifier, or personally identifiable information.

Manual setup is available through `setup.sh`; normal use should rely on `launch.sh`.
