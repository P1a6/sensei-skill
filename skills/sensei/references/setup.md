# Sensei first-run setup

Run this when `~/.claude/sensei/profile.md` does not exist (or the user says `sensei setup` / `sensei reset`). Nothing from the skill's repo is personal: every user's profile and curriculum are created here, on their own machine.

Keep it short: at most 5 questions, one per message, each with sensible defaults the user can accept with "default".

## Questions

1. **Goal.** What do you want to become or build? (junior web dev, backend, mobile, data/Python, a specific project, or a non-code subject). Default: junior web developer.
2. **Stack.** Which languages/tools do you want to learn? Offer the template's tracks (web frontend, backend and data, mobile, cloud and operations, extensions, LLM APIs, e-commerce) plus "other". Default: Foundations + Core + one language + the tracks matching the goal.
3. **Starting point.** Two options: (a) *ground zero* (default): every topic starts `new`, and nothing moves up without passing Stage 2/3; (b) *self-assessed*: user lists topics they believe they know, and each gets a short placement check (3 questions) before being set above `new`. Never accept claims without a check.
4. **Pace.** Sessions per week and rough minutes per session. Used only to suggest how many topics to plan; not enforced.
5. **Strictness.** Keep `skip` once per day (default) or change the limit. Record in config.

## Create files (all under `~/.claude/sensei/`, create the dir if missing)

- `config.md`: goal, stack, starting point, pace, skip limit, created date.
- `curriculum.md`: copy of `references/curriculum-template.md`, pruned and reordered for the answers. Show the user the resulting ordered topic list (ids and names only, no explanations) and ask once whether to add or remove anything. Topics the user names that are not in the template can be appended with new ids (use 100+) and prerequisites.
- `profile.md`: format from SKILL.md, every curriculum topic `new`, `last_skip: never`.

Then say what the first unlocked topic is and ask for the single feature to build (or propose one), continuing with Setup step 1 in SKILL.md. Do not teach any concept during setup.

## Reset and edit

- `sensei setup` again: re-run only the questions, update `config.md` and `curriculum.md`, keep `profile.md` levels for topics that still exist.
- `sensei reset`: confirm in chat first, then delete only `~/.claude/sensei/profile.md` and re-run setup. Never touch other files.
- The user may edit any of these files by hand; trust their edits.
