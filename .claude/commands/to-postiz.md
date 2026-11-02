---
description: Upload a finished OpenMontage render to self-hosted Postiz and create a DRAFT post (never scheduled)
argument-hint: <path-to-mp4> [caption]
---

Send a finished render to Postiz (https://postiz.flyk.pro) as a draft.

1. Check that the file at `$ARGUMENTS` (first token) exists and is an MP4 under `projects/`. If no path is given, list the newest `projects/*/renders/*.mp4` (or `projects/*/**/*.mp4`) and ask which one.
2. Check that `POSTIZ_API_URL` and `POSTIZ_API_KEY` are set without printing them. If they're missing, tell the user to set them (key from Postiz → Settings → Public API) and stop.
3. Upload: `postiz upload <file>` (install with `npm i -g postiz` if the CLI is missing). Keep the returned `.path`. Postiz only accepts its own uploaded paths.
4. Run `postiz integrations:list` and ask the user which channel(s) to use. For each one, run `postiz integrations:settings <id>` and follow its rules (TikTok: `content_posting_method: "DIRECT_POST"`).
5. Create a **draft**: `postiz posts:create -t draft -c "<caption>" -m "<uploaded path>" -s "<ISO date the user picks, default tomorrow 10:00 local>" -i "<integration ids>"`.
6. Report the draft id(s). The user promotes drafts to the schedule in Postiz. Never use `posts:status --status schedule` unless the user asks for it.
