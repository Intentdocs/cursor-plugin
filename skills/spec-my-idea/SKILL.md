---
name: spec-my-idea
description: Turn an app idea into an IntentDocs story map the founder reviews. Use when the person has an app idea or asks to spec a product in IntentDocs.
---

<!-- Generated from packages/docs/src/lib/spec-my-idea.ts by scripts/generate-cursor-plugin-skills.mjs. Do not edit by hand. -->

# Spec my idea

When the person has an app idea — "I've got an app idea" — follow these steps in order:
1. Agree a project name. Stop for the person before creating the project.
2. Call create_project with that name and a one-line idea. It creates the project in their personal workspace.
3. Ask the five vision questions one at a time and save each with set_vision (alias set_constitution). get_vision returns the next unanswered question with its heading and hint — ask that one in those words. One key is enough; the others stay. A different answer to a question that already has one needs confirm: true. Stop for the person after each vision question.
4. Draft the story map with create_stories.
5. Give the founder the review link create_stories returns.
6. Stop after handing over the draft link.

Stop for the person at three points: before creating the project, after each vision question, and after handing over the draft link.

Building a story follows the build loop that start_story hands over.

## The Spec my idea prompt

Spec my idea. The person has an app idea. Start this flow and follow the steps in order.

1. Agree a project name. Stop for the person before creating the project.
2. Call create_project with that name and a one-line idea. It creates the project in their personal workspace.
3. Ask the five vision questions one at a time and save each with set_vision (alias set_constitution). get_vision returns the next unanswered question with its heading and hint — ask that one in those words. One key is enough; the others stay. A different answer to a question that already has one needs confirm: true. Stop for the person after each vision question.
4. Draft the story map with create_stories.
5. Give the founder the review link create_stories returns.
6. Stop after handing over the draft link.

Stop for the person at three points: before creating the project, after each vision question, and after handing over the draft link.
