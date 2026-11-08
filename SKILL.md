---
name: chat-handoff
description: Saves a user's progress by turning the current conversation into a handoff document (done, not done, decisions, where they stopped, and a paste-ready prompt for a new chat). Use this skill whenever the user types "/handoff", says their chat or message limit is almost over, asks to save progress, wants to continue in a new chat or another chatbot, or asks for a summary of how much of a project is finished. Also use it when a conversation has become very long and the user may lose context soon, even if they don't say "handoff".
---

# Chat Handoff

Use this skill to help someone continue a project in a new chat without starting over.

## When to run

- The user types `/handoff` (or pastes a request for a handoff into an existing chat), or says things like "my limit is almost over", "save my progress", "I need to continue in a new chat".
- Once the conversation is long (roughly 15 to 20 exchanges), offer it once with: "Want me to create a handoff file now?" If the user declines or ignores the offer, wait before asking again.

## How to write it

Read the conversation, then produce a handoff with these sections, in this order:

1. **Project goal**: one or two lines on what the user is trying to achieve.
2. **Done so far**: bullets of what is finished.
3. **Not done yet**: bullets of what is pending, broken, or undecided.
4. **Key decisions**: choices made and the reason for each.
5. **Important content**: code, text, numbers, names, links, or settings from the chat that must not be lost. Copy these exactly, don't paraphrase.
6. **Where we stopped**: the exact point the work reached and what was about to happen next.
7. **Next steps**: the next 3 to 5 actions, in order.
8. **Paste-ready prompt**: a short message the user can paste into a new chat to continue. It must include the goal, the current state, the key content needed, and the next step, so it works on its own with no other context. Put it in a code block so it is easy to copy.

Add a one-line progress estimate near the top, such as "Roughly 60% done", based only on the conversation. If it cannot be judged, say so.

## Rules

- Do not ask questions first. Write the whole handoff in one reply, because the user may have almost no messages left.
- Only include what was actually discussed. Never invent details, files, or decisions.
- If something is unclear or unfinished, say that plainly instead of guessing.
- Be specific. Replace vague lines like "worked on the design" with what was actually done.
- Keep it readable in about two minutes, except for exact content in section 5, which can be as long as needed.
- Write in plain language. No filler.

## Output

- If you can create files, make a DOCX by default, or a PDF if the user asks for one. Use a clear name such as `handoff-<project-name>.docx` and share it.
- If you cannot create files, output clean formatted text that the user can copy into a document.
- After sharing, say in one line how to use it: start a new chat (or another chatbot) and paste the "Paste-ready prompt" section, and attach the file if the platform allows it.
