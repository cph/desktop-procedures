# Developing Features


#### Goals

These processes should ensure:
  1. that we're building that right thing
  2. that what we're building is reliable and maintainable
  3. that our progress is visible


#### Procedures

 - Product Teams with active roadmaps meet weekly for [Incubation](planning_releases/incubation.md). These meetings allow teams to check in frequently and to refine plans.
 - We [slice tasks](developing_features/task_slicing.md) before writing code to help us identify questions (and obstacles) early and set realistic goals.
 - We write code according to our [style guides](https://github.com/cph/style-guides) so our codebases are as readable as possible.
 - We [guard critical logic with unit tests](developing_features/automated_tests.md) to protect against regressions and to support refactoring.
 - We make changes ["Hot Compatible"](developing_features/hot_compatibility.md), work on [topic branches](developing_features/git_flow.md), and [create Pull Requests](developing_features/pull_requests.md) to facilitate [testing, code-reviewing, and deploying our changes](deploying_changes.md)


#### Related Topics

 - [Planning Releases](planning_releases.md)
 - [Deploying Changes](deploying_changes.md)
 - [Updating our Icon Fonts](designing_products/ui_guide/icon_fonts.md)
