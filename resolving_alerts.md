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
- The different types of alerts have different target time frames:
  - **Questions**, **Regressions**, and **Lies** that are sent to us by support (via Zendesk) have a target time frame of **2 business days**
  - **Security Vulnerabilities** and **Exceptions** have a target time frame of **5 business days**
- In general, we choose to prioritize alerts coming from Support so as to both support our teammates and to ensure a good customer experience.

##### Interacting with alerts from Zendesk
  1. "Claim" the alert by assigning it to yourself in Jira.
  2. When the ticket is resolved or if you have questions for the support technician, you'll have to opt to "CC" yourself on the ticket in Zendesk. This will allow you to post internal notes back to the tech.
  3. Always make sure to post a short resopnse in Zendesk before assigning back to the technician.
  4. Use `ep zendesk:assign` to actually reassign the ticket back to the appropriate tech when you have a question or if the ticket has been resolved. 

##### Interacting with alerts from Sentry
  1. "Claim" the alert by assigning it to yourself in Jira.
  2. If the exception is infrequent or known to be caused for benign reasons, you can choose to archive in Sentry. (NB: "Benign" exceptions are considered a code smell and should be refactored out as time allows)
  3. Make a PR to address the issue following our usual process.
  4. Once the PR is merged and deployed, mark the alert as resolved in Sentry.

##### Interacting with CVEs (Common Vulnerabilities and Exposures)
  1. "Claim" the alert by assigning it to yourself in Jira.
  2. Make a PR to address the issue following our usual process.
  3. Some vulnerabilities can't be addressed or are unused by our codebase. In this case, we can choose to "Dismiss" the alert in GitHub (Security > Dependabot Alerts)
  4. Once the PR is merged, the alert should resolve automatically.

   > If an alert is going to take longer than a few hours to fix, the developer fielding it should see if the problem can be addressed _now_ with a shallower solution while deferring a deeper solution to Roadmapping. If a shallower solution isn't available, the developer should work with their Manager to figure out if the Alert should be deferred until we can define a solid rubric for that here.
   >
   
   > If an Exception is both unreproducible _and_ didn't affect the customer's experience (e.g. it was raised from a background job that was subsequently retried), the alert can be ignored.

 - If an issue is small, clearly-defined, and not urgent (i.e., it neither qualifies as an alert nor needs full incubation or roadmapping), it _may_ be considered a "bug" and added to the list of Refactor Tasks, which may be drawn from during built-in downtime on the roadmap.
 - We follow our [style guides](https://github.com/cph/style-guides) to make it as easy as possible to read each other's code (as during code review, troubleshooting, or getting familiar with a new project)
 - We [guard critical logic with unit tests](developing_features/automated_tests.md) to protect against regressions and to support refactoring.
 - We make changes ["Hot Compatible"](developing_features/hot_compatibility.md), work on [topic branches](developing_features/git_flow.md), and [create Pull Requests](developing_features/pull_requests.md) to facilitate [testing, code-reviewing, and deploying our changes](deploying_changes.md)


#### Tools

 - [Alerts Dashboard](https://ep-grand-central.herokuapp.com/dashboards/alerts?scroll=1)
 - [Jira Backlog](https://concordiapublishing.atlassian.net/jira/software/projects/EP/boards/5/backlog)
 - [Sentry](https://cphep.sentry.io)
 - GitHub Dependabot Alerts (accessed per repository)


#### Related Topics

 - [Deploying Changes](deploying_changes.md)
