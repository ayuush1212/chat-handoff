# Changelog

## 1.0.0

- Added a structured handoff for projects that need to continue in a new chat.
- Added a plain `SKILL.md` for direct Codex installation.
- Kept the packaged `chat-handoff.skill` for platforms that accept skill archives.
- Added a portable prompt for chatbots that use custom instructions.
- Added package validation in GitHub Actions.

## 1.1.0

- README rewritten for first-time users, with a copy-and-paste option and a direct skill download link.
- Handoff now runs immediately when the prompt is pasted into an existing chat.
- Handoff is written in one reply, since the user may be nearly out of messages.
