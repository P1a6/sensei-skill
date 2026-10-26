# Sensei

A Claude Code skill that teaches while it builds. Instead of handing you finished code, Sensei builds one small feature with key parts deliberately missing, then gates your understanding in three stages: **research**, **interview**, **fill-in-the-blanks**. The goal state is junior-developer knowledge.

Trigger it by saying "sensei", "teach me", or "make sure I understand".

## Install

As a plugin (recommended):

```
/plugin marketplace add P1a6/sensei-skill
/plugin install sensei@sensei
```

Or manually:

```
git clone https://github.com/P1a6/sensei-skill
cp -r sensei-skill/skills/sensei ~/.claude/skills/sensei
```

## First run: setup

The first time you run `/sensei`, it walks you through a short setup (5 questions at most, defaults available):

1. Your goal (e.g. junior web dev, backend, mobile, a specific project)
2. The stack you want to learn
3. Your starting point: ground zero, or self-assessed with a placement check
4. Your pace
5. Skip strictness

It then builds **your own curriculum** from the bundled template and creates your profile. Nothing is shared between users: the repo contains only the generic template.

Re-run any time with `sensei setup` (change goal/stack, keep progress) or `sensei reset` (wipe your progress, after confirmation).

## What it stores (on your machine only)

- `~/.claude/sensei/config.md`: your goal and settings
- `~/.claude/sensei/curriculum.md`: your personal curriculum
- `~/.claude/sensei/profile.md`: your cross-project progress
- `.sensei/state.md` in a project: state of the current task

All are created during setup or on first use. Add `.sensei/` to your project's `.gitignore` if you don't want it committed.

## License

MIT
