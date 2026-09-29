# Prototype: Progress Log (technical probe)

**What it is:** A basic version of a personal workout tracker that Jack Yousey built for himself and has used since May 2026. It's a Flask web app. The code is in [`progress-log/`](progress-log/), with setup steps in [`progress-log/README.md`](progress-log/README.md).

**Why it's here:** It's a real, working example of one team member trying to keep his fitness information in one place. It's a starting point for questions, not our proposed solution.

## What it covers today

| Area | In this basic version? |
|---|---|
| Strength training | Yes: workouts, sets, templates, exercise bank, PRs, progress charts |
| Cardio | Yes: sessions, distance, pace, splits, heart rate, calories burned |
| Diet | **No** |
| Overall fitness | Yes: body weight, sleep, rest days, streaks, weekly notes, stats, goals |
| AI | **Not inside the app.** Jack gets a weekly AI review from a separate Claude scheduled task that reads his week's workouts and posts a note to the app. |

## What it helps us see

- **Data entry is manual.** Jack built it to "compile all the data from different apps," but he types his data in by hand. Pulling data in automatically from other apps is a dependency we don't understand yet.
- **Diet is a team assumption.** Our problem includes diet, but the one working tool on the team leaves it out and its user doesn't miss it. Do other gym goers want diet in the same place?
- **What would the AI do?** Here, AI feedback is a weekly summary layered on top of logged data. Is that what gym goers want, or do they need help *during* a workout (e.g., when equipment is busy)?
- **Built for one person.** It fits one experienced user's habits. We don't know whether it fits beginners or other gym goers.

## How we could use it in a stakeholder test

Show the app, or screenshots of it, to a gym goer and ask what they would use, what's missing, and whether they'd enter data by hand. Jack reports that people he has shown it to informally wanted something similar. Those reactions weren't recorded, so testing this properly is the next step.

## Limits

- This is a **basic version**. The version Jack uses day to day has changed since and wasn't included.
- No personal workout data, passwords or keys are included. The app reads all secrets from environment variables, and its database file is git-ignored.

## Provenance

- **Author:** Jack Yousey (personal project, shared with the group as a prototype).
- **Source:** snapshot of the basic version's code as of 2026-09-24 (commit `de9013e` in Jack's personal repository). Earlier history is not included.
- **AI assistance in building the app:** Jack used Claude (Anthropic) to build the app.
- **AI assistance in preparing this folder:** Claude Code (Claude Opus 5.5) reviewed the code read-only, drafted this README from Jack's answers and his first-contribution note in the private working repository, and copied the files. Jack approved adding it to this repository.
- **Libraries:** Flask, gunicorn, psycopg2-binary, openpyxl (see `progress-log/requirements.txt`).
