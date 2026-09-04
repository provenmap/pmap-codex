---
category: connect
description: "Account · Update this plugin to the latest published version"
allowed-tools: Bash(node:*)
---

Update **ProvenMap Architect** (`pmap-architect`) to the latest version published for
**Codex**. The script looks up the plugin's actual installed marketplace and scope and
updates it directly — it does not guess or retry blindly.

## Update workflow

Run the update script:

```bash
node ${PLUGIN_ROOT}/scripts/pmap-update.js --host codex --plugin-name pmap-architect --host-name "Codex"
```

Print the JSON `display` field **verbatim in your reply** — the Bash output panel is collapsed for
the user, so write it out in full. It already states old → new version (or the reason it couldn't
update). Do not reformat it, and do not state a version number yourself beyond what `display` says.

If the script exits non-zero, `display` already explains what went wrong (marketplace refresh
failed, plugin not found under any scope, or the update command itself failed) — relay it as-is
rather than guessing at a fix or retrying with different flags.

**Outcome:** `node ${PLUGIN_ROOT}/scripts/pmap-architect.js --brief --command update` → one line, per `${PLUGIN_ROOT}/knowledge/outcome/SKILL.md`.
