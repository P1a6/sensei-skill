# Sensei

A Claude Code skill that teaches while it builds. Instead of handing you finished code, Sensei builds one small feature with key parts deliberately missing, then gates your understanding in three stages: **learn**, **interview**, **fill-in-the-blanks**. The goal state is junior-developer knowledge.

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

## Learn anything, anywhere

Sensei works for any subject (coding, languages, music theory, statistics...) and in two places:

- **Claude Code**: progress is saved in files on your machine.
- **Normal chat (claude.ai / desktop)**: upload the skill (Settings > Capabilities > Skills, zip of the `skills/sensei` folder). Progress is saved in a **Sensei card**: a short text block Sensei prints after setup and after each lesson. Save it, and paste it at the start of your next chat.

## How a lesson works

1. **Story intro**: a few lines placing the lesson in the bigger picture (`Domain > Section > Topic > lesson`), with one small analogy.
2. **Stage 1, learn**: Sensei teaches 3-5 concepts one at a time: definition, how it works, a tiny example and the gotchas, then a quick check you answer before moving on. At the end you get search keywords to go deeper. Say `done` when ready.
3. **Stage 2, interview**: 5 questions (easy to hard), each with 2-3 sub-questions. Every question is worth 10 points, no weights, and passing needs 30 of 50, so strong answers on the hard question alone can't carry you.
4. **Stage 3, fill in the blanks**: you write the key parts Sensei left out, then answer 2 questions about the rest.
5. **Feedback**: after each lesson you get a report: scores per question, what you learned, what went well, what to work on, your trend over recent lessons, and the next step. It's saved as a note per lesson. Say `sensei review` any time for the picture across all sessions.

## First run: setup

The first time you run `/sensei`, it walks you through a short setup (5 questions at most, defaults available): your subject and goal, scope, starting point (ground zero or self-assessed with placement checks), pace, and skip strictness.

It then builds **your own curriculum** (from the bundled template for coding, generated from scratch for other subjects) and creates your profile. Nothing is shared between users: the repo contains only the generic template.

Words you type inside a session: `done` (end Stage 1), `skip` (skip a stage, once per day), `reveal` (show the answer), `sensei setup`, `sensei reset`, `sensei new track`, `sensei track <name>`, `sensei tracks`, `sensei review`, `sensei card` (chat).

## What it stores (on your machine only, Claude Code)

- `~/.claude/sensei/config.md`: small pointer file with global settings and `data_dir`
- `<data_dir>/tracks/<subject>/`: config, curriculum, profile, lesson log and a feedback note per lesson (`sessions/`) for each subject you learn
- `<data_dir>/Sensei.md`: home note with links and progress per track (Obsidian)

`data_dir` defaults to `~/.claude/sensei`. Point it at a folder in an **Obsidian vault** during setup (or later with `sensei vault <path>`) and all your learning data become normal notes you can read, edit and graph, shared by every session. Sensei detects the vault (a `.obsidian` folder) and keeps the home note up to date.
- `.sensei/state.md` in a project: state of the current lesson

Add `.sensei/` to your project's `.gitignore` if you don't want it committed.

## License

MIT
