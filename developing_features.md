# Developing Features


#### Goals

These processes should ensure:
  1. that we're building that right thing
  2. that what we're building is reliable and maintainable
  3. that our progress is visible


#### Procedures

 - [Product Teams](the_product_team.md) with active roadmaps meet weekly for [Incubation](incubation.md). These meetings allow teams to check in frequently and to refine plans.
 - After Incubation meetings, developers [plan their next week's Sprint](developing_features/sprint_planning.md). This process helps us to identify obstacles early and sets a team goal for the following week.
 - We write code according to our [style guides](https://github.com/cph/style-guides) so our codebases are as readable as possible.
 - We guard critical logic with [unit tests](test_driven_development.md) to protect against regressions and to support [refactoring](refactoring.md).
 - We make changes ["Hot Compatible"](hot_compatibility.md), work on [topic branches](git_flow.md), and [create Pull Requests](pull_requests.md) to facilitate [testing, code-reviewing, and deploying our changes](deploying_changes.md)


#### Related Topics

 - [Planning Releases](planning_release.md)
 - [Deploying Changes](deploying_changes.md)
