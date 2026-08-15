---
description: Launch a browser-based voice interview and produce deployment-discovery.json.
allowed-tools: [Bash, Read, Write]
---

# Launch the interview within 30 seconds

1. Run `bash skills/interview/launch.sh` in the background.
2. Read the printed `http://127.0.0.1:<port>/talk.html` URL and give it to the user. The browser should open automatically. If it does not, ask the user to open the URL, allow microphone access, start the interview, and end it when complete.
3. Do not read additional implementation files before launch. `launch.sh` manages the environment, agent, and local server.
4. After the user confirms completion, fetch the transcript:

```bash
.venv/bin/python skills/interview/scripts/fetch_transcript.py
```

5. Build `skills/interview/output/deployment-discovery.json` according to `skills/interview/references/discovery-spec.md`. Preserve missing evidence under `open_questions` or `unknown`.
6. Validate the contract and stop if it fails:

```bash
.venv/bin/python skills/interview/scripts/validate_discovery.py \
  skills/interview/output/deployment-discovery.json
```

7. Summarize integration tier, automation priorities, product gaps, and unresolved evidence before handing the record to the report skill.
