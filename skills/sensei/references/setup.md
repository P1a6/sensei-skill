# Sensei first-run setup

Run this when the global config / active track is missing (file mode), when the user has no Sensei card (chat mode), or on `sensei setup`, `sensei reset`, `sensei new track`. Nothing from the skill's repo is personal: every user's tracks, profile and curriculum are created here, for them only.

Keep it short: at most 5 questions, one per message, each with a sensible default the user can accept with "default".

## Questions

1. **Subject and goal.** What do you want to learn, and what should you be able to do at the end? Any subject works (web dev, Spanish, music theory, statistics, investing basics, a specific project...). Default: junior web developer.
2. **Scope.** Coding subject: which languages/tools? Offer the template's areas (web frontend, backend and data, mobile, cloud and operations, extensions, LLM APIs, e-commerce) plus "other". Any other subject: which parts matter most, and anything to skip? Default: whatever matches the goal.
3. **Starting point.** (a) *ground zero* (default): every topic starts `new`, nothing moves up without passing Stage 2/3; (b) *self-assessed*: the user lists topics they believe they know, and each gets a short placement check (3 questions) before being set above `new`. Never accept claims without a check.
4. **Pace.** Sessions per week and rough minutes per session. Only used to suggest how many topics to plan; not enforced.
5. **Strictness.** Keep `skip` once per day (default) or change the limit.

On `sensei new track`, ask only questions 1-3 and keep the global settings.

## Build the curriculum

- **Coding subject:** copy `references/curriculum-template.md`, prune and reorder it for the answers. Drop topics outside the scope; keep prerequisites consistent. Extra topics the user names get ids 100+ with prerequisites.
- **Any other subject:** do NOT use the coding template. Generate 15-40 topics in the same format (`id | topic | needs`), grouped under section headings (`## A. Name`) that read like chapters of the subject, ordered so each topic's prerequisites come earlier. One topic = one lesson-sized chunk. Mark purely conceptual topics `(concept)`. End with a one-line milestone describing the goal state (what "done" means). Keep topic names plain; no explanations.
- Show the user the ordered list (ids and names only, no explanations) and ask once whether to add, remove or reorder anything.

## Create files

**File mode** (under `~/.claude/sensei/`, create dirs if missing; `<track>` is a short slug of the subject):
- `config.md` (global; create only if missing): `skip_limit`, `last_skip: never`, `active_track`, `tracks:` list, created date.
- `tracks/<track>/config.md`: goal, scope, starting point, pace, created date.
- `tracks/<track>/curriculum.md`: the curriculum, with the milestone line.
- `tracks/<track>/profile.md`: format from SKILL.md, every topic `new`.

**Chat mode:** build the Sensei card (format in SKILL.md) with the curriculum, every topic `new`, and print it. Tell the user: "Save this card. Paste it at the start of future chats."

Then say what the first unlocked topic is and ask for the single lesson to build (or propose one), continuing with "Lesson setup" in SKILL.md. Do not teach any concept during setup.

## Switch, reset and edit

- `sensei track <name>`: set `active_track` (file mode) or load that track's card (chat mode). `sensei tracks` lists them.
- `sensei setup`: re-run the questions for the active track, update its `config.md` and `curriculum.md`, keep profile levels for topics that still exist.
- `sensei reset`: confirm in chat first, then delete only the active track's `profile.md` and rebuild it from its curriculum (all `new`). Never touch other files or tracks.
- `sensei card` (chat mode): print the current card.
- The user may edit any of these files by hand; trust their edits.
