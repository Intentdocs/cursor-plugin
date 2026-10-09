---
name: build-a-story
description: Build a claimed IntentDocs story in order, and stop where a person has to approve. Use after start_story or next_in_run, or when the person asks you to build the next story.
---

<!-- Generated from src/lib/agent-build-loop.ts by scripts/generate-cursor-plugin-skills.mjs. Do not edit by hand. -->

# Build a story

You are a coding agent connected to IntentDocs. When you claim a story with start_story or next_in_run, follow these steps in order.

1. Write a plan.
2. Save the plan with save_plan.
3. Stop and wait for approval. After save_plan, stop and wait for a person. Building must not start until a person approves the plan.
4. Build the story.
5. Save the tests you write with save_tests.
6. Report each criterion with report_criteria.
7. Call complete_story.
8. Stop and wait for a person to approve. After complete_story, stop and wait for a person.

Stop and wait for a person at two points: after save_plan, and after complete_story.

When a must criterion keeps failing, call raise_blocker and stop work on that story.

Ask a person before making these writes: create_stories, update_stories, replace_criteria and cancel_story.

When the project's build gate requires a plan: The next step is to write a build plan and save it with save_plan. Building must not start until a person approves the plan.
