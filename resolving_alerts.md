# Resolving Alerts


#### Rationale

There are some tasks that do not fit our process of [planning releases](planning_releases.md) for two reasons:
  1. they need to be resolved quickly for us to maintain a particular promise to our customers (i.e. of Support or Security)
  2. they tend to be smaller tasks (minutes/hours of effort rather than days/weeks)

The Alerts process creates a shortcut around [Roadmapping](planning_releases/roadmapping.md) to improve our response time for relatively urgent issues while cutting down on unnecessary process.


#### Goals

These processes should ensure:

 1. that regressions, questions from the Support Team, and security vulnerabilities are resolved quickly
 2. that processes involving Alerts (creating, assigning, scheduling, and resolving them) are exceptionally lightweight
 3. that the Alerts "shortcut" isn't abused for work that ought to be [roadmapped](planning_releases/roadmapping.md)


#### Procedures

 - We treat the following as Alerts:
    - **Questions from the Support Team**
    - **Regressions:** behavior that we unintentionally removed or broke in a recent release
    - **Security Vulnerabilities**
    - **Exceptions**
    - **Lies:** when a product gives false information in a report
 - We assign Alerts quickly to give the assigned developer as much time as possible to work on it.
 - We strive to close alerts within 2 business days.
   > If an alert is going to take longer than a few hours to fix, the developer fielding it should see if the problem can be addressed _now_ with a shallower solution while deferring a deeper solution to Roadmapping. If a shallower solution isn't available, the developer should work with their Manager to figure out if the Alert should be deferred until we can define a solid rubric for that here.
   >
   > If a CVE is identified for one of our dependencies, but the vulnerability could not actually be exploited in our codebase, the alert can be closed.
   >
   > If an Exception is both unreproducible _and_ didn't affect the customer's experience (e.g. it was raised from a background job that was subsequently retried), the alert can be ignored.
 - If an issue is small, clearly-defined, and not urgent (i.e., it neither qualifies as an alert nor needs full incubation or roadmapping), it _may_ be labelled as a `bug` instead of an `alert` and added to the list of Refactor Tasks, which may be drawn from during built-in downtime on the roadmap.
 - We follow our [style guides](https://github.com/cph/style-guides) to make it as easy as possible to read each other's code (as during code review, troubleshooting, or getting familiar with a new project)
 - We [guard critical logic with unit tests](developing_features/automated_tests.md) to protect against regressions and to support refactoring.
 - We make changes ["Hot Compatible"](developing_features/hot_compatibility.md), work on [topic branches](developing_features/git_flow.md), and [create Pull Requests](developing_features/pull_requests.md) to facilitate [testing, code-reviewing, and deploying our changes](deploying_changes.md)


#### Tools

 - Alerts [Here](https://ep-grand-central.herokuapp.com/dashboards/alerts?scroll=1)


#### Related Topics

 - [Deploying Changes](deploying_changes.md)
