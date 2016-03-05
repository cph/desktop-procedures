# Resolving Alerts


#### Rationale

There are some changes (like fixing a bug for a customer or applying a patch for a recently-disclosed exploit) that do not fit our process of [planning releases](planning_releases.md) for two reasons: (1) they need to be resolved in a smaller time frame in order for us to maintain a particular promise to our customers (i.e. of Support or Security); and (2) they tend to be smaller tasks (minutes/hours of effort rather than days/weeks) so that [Roadmapping](planning_releases.md) would be overkill for scheduling them.


#### Goals

Our Alerts process should ensure:
  1. that bugs blocking Customer Success with the product's current feature set, regressions, questions from the Support Team, and security vulnerabilities are resolved quickly
  2. that processes involving Alerts (creating, assigning, scheduling, and resolving them) are exceptionally lightweight
  3. that the Alerts "shortcut" isn't abused for work that ought to be [roadmapped](planning_releases.md)


#### Procedures

 - We monitor the [Alerts Dashboard](http://houst.in/alerts/dashboard) or the #alerts channel in Slack and assign them quickly so that developers have as much leeway as possible to manage their own time for closing alerts.
 - We strive to [close alerts](closing_alerts.md) within 2 business days.
 - We write code according to our [style guides](https://github.com/cph/style-guides) so our codebases are as readable as possible.
 - We guard critical logic with [unit tests](test_driven_development.md) to protect against regressions and to support [refactoring](refactoring.md).
 - We make changes ["Hot Compatible"](hot_compatibility.md), work on [topic branches](git_flow.md), and [create Pull Requests](pull_requests.md) to facilitate [testing, code-reviewing, and deploying our changes](deploying_changes.md)


#### Related Topics

 - [Deploying Changes](deploying_changes.md)
