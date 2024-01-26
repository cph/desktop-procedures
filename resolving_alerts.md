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

 We prioritize Zendesk Alerts from CTS and strive to close then in two days either by:
    - Releasing a bug fix
    - Fixing any data issues
    - Fixing any system issues
    - Create a small batch item if the bug is non-critical

  Interacting with Zendesk tickets
      1.  Assign the Github issue generated for the ticket to yourself
      2.  Use `ep zendesk:assign` to push the ticket back to the tech when you have a question or if the ticket has been resolved. 

  We resolve CVE (Common Vulnerabilities and Exposures) as follows:
    - If it can be exploited in our codebase it is addressed immeaditely, otherwise it can wait till a cooldown/refactor time.

  We keep an eye on any Sentry alerts so that:
    - We may resolve any system errors in a timely manner
    - Identify bugs that need immediate attention
    - Identify bugs that can be part of a small batch

  Interacting with CVEs and Sentry alerts
    1. Assign the Github issue generated for the CVE or Sentry alert to yourself.
    2. If you create a PR for it, associate the PR with the Github issue; once the PR is merged the Github issue is closed.
    3. For Sentry alerts, resolving them or archiving them automatically closes the Github issue

   > If an alert is going to take longer than a few hours to fix, the developer fielding it should see if the problem can be addressed _now_ with a shallower solution while deferring a deeper solution to Roadmapping. If a shallower solution isn't available, the developer should work with their Manager to figure out if the Alert should be deferred until we can define a solid rubric for that here.
   >
   
   > If an Exception is both unreproducible _and_ didn't affect the customer's experience (e.g. it was raised from a background job that was subsequently retried), the alert can be ignored.
 
 - We follow our [style guides](https://github.com/cph/style-guides) to make it as easy as possible to read each other's code (as during code review, troubleshooting, or getting familiar with a new project)
 - We [guard critical logic with unit tests](developing_features/automated_tests.md) to protect against regressions and to support refactoring.
 - We make changes ["Hot Compatible"](developing_features/hot_compatibility.md), work on [topic branches](developing_features/git_flow.md), and [create Pull Requests](developing_features/pull_requests.md) to facilitate [testing, code-reviewing, and deploying our changes](deploying_changes.md)


#### Tools

 - [Alerts Dashboard](https://ep-grand-central.herokuapp.com/dashboards/alerts?scroll=1)
 - [Sentry Alerts](https://github.com/issues?q=is%3Aopen+user%3Acph+label%3Asentry+-label%3Abug+sort%3Acreated-desc)


#### Related Topics

 - [Deploying Changes](deploying_changes.md)
