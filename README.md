# Comedy Writers Room

A Claude Code skill that demonstrates subagents by having one write jokes while three others play audience members reacting to them.

[![Watch the video](https://substack-video.s3.amazonaws.com/video_upload/post/185286108/38e36ff7-f8fa-45f5-bf2f-6688d800543b/transcoded-48883.png)](https://www.talraviv.co/p/i-wanted-to-understand-subagents)

## Why subagents?

Subagents are the equivalent of you opening additional side chats while using ChatGPT.

Say you're in a ChatGPT conversation (e.g. plan a surf trip), but you need to research something on the side (e.g. what wetsuit am I ok with). You don't want to derail the main thread, so you open a new tab, ask your question there, get an answer, then bring just the bottom line back to your original conversation.

**That's a subagent.** When Anthropic built "subagents" into Claude Code, they automated that plumbing. (If this sounds a lot like calling a tool, you're right. Manus calls this "[agent-as-a-tool](https://youtu.be/6_BcCthVvb8?si=3PscXsLC49odFlVk&t=2429)")

"Fresh side chats" are valuable for two reasons:

1. **Keep side quests from polluting the main agent context window** — you just need the answer, not the research/discussion that got there

2. **Get a fresh pair of eyes** — if you want code review, or an eval, or a second opinion, you don't want the same context window that came up with the answer to also judge it. ([Zevi Arnovitz did this manually](https://www.lennysnewsletter.com/p/the-non-technical-pms-guide-to-building-with-cursor) long before it was a feature.)

## How to use

1. Copy this skill folder to `~/.claude/skills/`
2. Open Claude Code in any directory
3. Ask it to write a joke about any topic

## What you'll see

Watch from two camera angles:

1. **The terminal** — you can see Claude Code spawn a "writer" subagent, then three "audience" subagents

2. **The files on your computer** — navigate to `~/.claude/projects` and watch Claude Code create the main thread, writer subagent, three audience subagents, and another writer subagent to act on their feedback.

Even though these look like scary "JSONL" files, they're just text files containing chat history, human-readable if you open them with this [prettifier extension](https://marketplace.visualstudio.com/items?itemName=gabor.jsonl-gazelle).

Watching the files appear in real time makes it click: subagents aren't magic. They're just opening another chat thread, getting an answer, and bringing just the bottom line back into the main thread.

Text files all the way down.

## Note on iteration limit

This repository currently limits feedback to just one round (three personas react once, writer revises once). This keeps demos short.

To let it keep iterating agentically until the jokes actually land, remove this line from SKILL.md:

    **TESTING: Limit to 1 round of feedback for now.**
