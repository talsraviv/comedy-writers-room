# Comedy Writers Room

A Claude Code skill that demonstrates the use of subagents as an educational exercise.

The idea: one subagent writes a joke, then three subagents each represent a different fresh pair of eyes receiving the joke and returning a reaction. The writer iterates based on feedback.

## How to use

1. Copy this skill folder to ~/.claude/skills/
2. Open Claude Code in any directory
3. Ask it to write a joke about any topic

Watch the subagents spawn in series - you can inspect each one as it happens.

[VIDEO PLACEHOLDER]

## Note on iteration limit

This repository currently limits feedback to just one round (three personas react once, writer revises once). This keeps demos short.

To let it keep iterating agentically until the jokes actually land, remove this line from SKILL.md:

    **TESTING: Limit to 1 round of feedback for now.**
