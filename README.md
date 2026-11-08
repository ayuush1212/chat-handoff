# Chat Handoff

**Never lose your project when a free chat limit runs out.**

Type `/handoff` and your chatbot writes a short file that says what is done, what is not, and where you stopped. It also gives you one prompt to paste into any new chat, so you can keep going without explaining everything again.

Free to use. Works with Claude, ChatGPT, Gemini, and any chatbot that lets you paste text.

---

## Use it in 1 minute

Pick the way that matches your chatbot.

### Option A: Any chatbot (easiest, nothing to install)

1. Copy the prompt in the box below. The copy button is in the top right corner of the box.
2. Paste it into the chat you are working in and send it. It writes your handoff right away.
3. Copy the **Paste-ready prompt** from the result, open a new chat (or another chatbot), paste it, and carry on.

```text
# Chat Handoff

Help the user carry a project from this chat into a new one. Write a clear handoff before the conversation gets cut off, so the user does not have to explain the whole project again.

WHEN TO RUN
- If this text was just pasted into a chat that already has a conversation in it, create the handoff immediately. Do not wait to be asked again.
- Run when the user types "/handoff" or says the chat limit is getting close.
- Once a conversation is long (roughly 15 to 20 messages), you may ask: "Want me to create a handoff file now?" If the user ignores that, do not keep asking.

HOW TO WRITE IT
Read the conversation and create a handoff with these sections, in this order:

1. Project goal: one or two lines on what the user is trying to achieve. Add a one-line progress estimate (for example "Roughly 60% done") based only on the conversation.
2. Done so far: a bulleted list of what is finished.
3. Not done yet: a bulleted list of what is still pending or broken.
4. Key decisions: choices that were made and the reason for each.
5. Important content: code, text, numbers, names, links, or settings that must not be lost. Copy these exactly.
6. Where we stopped: the exact point the work reached, and what was about to happen next.
7. Next steps: the next 3 to 5 actions, in order.
8. Paste-ready prompt: a short message the user can paste into a new chat. Include the goal, current state, important content, and next step so it works without this conversation. Put it in a code block so it is easy to copy.

RULES
- Do not ask questions first. Write the whole handoff in ONE reply, because the user may have almost no messages left.
- Only include things that were actually discussed. Never invent details.
- If something is unclear or unfinished, say so instead of guessing.
- Keep it specific. Avoid vague lines like "worked on the design."
- Keep it short enough to read in about two minutes, except for exact content in section 5.

OUTPUT
- If you can create files, produce a DOCX. Use a PDF only when the user asks for one.
- If you cannot create files, return clean formatted text the user can copy into a document.
```

Want it ready every time? Save the same text as a custom instruction, a custom GPT, or a Gem if your chatbot offers one, then just type `/handoff` whenever you need it.

### Option B: Claude Skill

1. [Download chat-handoff.skill](https://github.com/ayuush1212/chat-handoff/raw/main/chat-handoff.skill).
2. In Claude, open your settings, find Skills, and upload the file.
3. In any chat, type `/handoff`.

If you do not see a Skills option on your plan, use Option A. It works in Claude too.

### Option C: Codex and other agent tools

Use the `SKILL.md` file in this repo as the skill. Then type `/handoff`.

---

## What you get

1. Project goal and a rough progress estimate
2. What is done
3. What is not done
4. Key decisions and why
5. Important code, links, names, and numbers, copied exactly
6. Where you stopped
7. Next steps
8. A prompt you can paste into a new chat

See a full example: [examples/sample-handoff.md](examples/sample-handoff.md)

## Tips

- Run it **before** you get cut off. When a chat starts to feel long, or you have a few messages left, type `/handoff`.
- If the chatbot cannot make files, it gives you text. Paste that into Google Docs or Word.
- Skim the result before relying on it. Chatbots can miss details in a very long chat.

## Already locked out?

Copy the conversation text from your chat, open another chatbot, paste the prompt from Option A, then paste your conversation below it and send.

## Limits

- It cannot see your real remaining limit. It works when you type `/handoff`, and it may offer a handoff when a chat gets long.
- Quality depends on the chatbot you use. Weaker free models may miss details.

## License

MIT. Use it, change it, share it.

## Contributing

Small fixes are welcome. The same instructions live in three places: `SKILL.md`, `handoff-prompt.txt`, and `chat-handoff.skill`, and the prompt is also shown in this README. Please keep them in sync. A check runs on every pull request to verify the packaged skill matches `SKILL.md`.
