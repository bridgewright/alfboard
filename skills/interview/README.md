# Interview Runtime

This skill conducts a Korean browser-based voice interview and converts the transcript into a structured deployment discovery contract.

## Quick start

```bash
cp skills/interview/.env.example skills/interview/.env
# Add ELEVENLABS_API_KEY to the local .env file.
bash skills/interview/setup.sh
bash skills/interview/launch.sh
```

`launch.sh` creates or reuses the virtual environment, verifies the configured agent, starts the local browser server, and prints the interview URL.

## Outputs

- A turn-level transcript and interview notes under ignored local output paths
- `deployment-discovery.json`, the validated handoff contract for deployment reporting

The interviewer seeks a recent concrete event, frequency, current workaround, system dependency, organizational owner, measurable effect, and unresolved constraint. It identifies the participant's role at the beginning of the conversation.

## Privacy

Real transcripts may contain personal, confidential, or commercially sensitive information. Keep `.env`, transcript, and output directories outside version control. Committed examples must be fictional.

## Key files

| File | Purpose |
| --- | --- |
| `launch.sh` | End-to-end local launch |
| `setup.sh` | Initial environment and agent setup |
| `prompt/interviewer-system-prompt.md` | Korean runtime behavior for the interviewer |
| `references/discovery-spec.md` | Discovery contract |
| `scripts/validate_discovery.py` | Deterministic contract gate |
| `assets/sample-discovery.json` | Fictional sample input |
