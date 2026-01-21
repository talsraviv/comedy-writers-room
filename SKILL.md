---
name: comedy-writers-room
description: Use when helping write stand-up comedy, jokes, or humorous material about any topic
---

# Comedy Writers Room

Write jokes using subagents as a simulated audience. One agent writes, three agents react as different personas, then iterate based on their feedback.

## Process

### Step 1: Dispatch the writer

Read `writer-prompt.md` and use that template to dispatch a subagent.
- Replace `[TOPIC]` with the user's topic
- For first draft, omit the revision section

### Step 2: Dispatch all 3 audience members in series

Read each audience template and dispatch them one at a time:
1. `audience-enthusiast-prompt.md`
2. `audience-skeptic-prompt.md`
3. `audience-overthinker-prompt.md`

Replace `[JOKES]` with the jokes from the writer.

### Step 3: Synthesize feedback

Read what each persona said. What landed? What fell flat? What confused people?

### Step 4: Dispatch writer again with feedback

Use `writer-prompt.md` again, this time:
- Include the revision section
- Replace `[FEEDBACK]` with the synthesized audience reactions

### Step 5: Repeat steps 2-4 until the jokes land

Stop when the personas are reacting well.

**TESTING: Limit to 1 round of feedback for now.**

### Step 6: Present final material to user

Include a brief summary of how it evolved - what got cut, what emerged from iteration.

## Critical Rules

- **Always use Task tool** - Never shell out to `claude` CLI
- **Dispatch audience in series** - One at a time, so each reaction is visible
- **Include feedback in revisions** - The writer needs to know what to fix
