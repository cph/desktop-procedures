# [Deploying Changes](../deploying_changes.md) / Code Review


#### Tools Used

 - Houston's [Pulls Kanban](http://houst.in/dashboards/pulls) or [Pulls View](http://houst.in/pulls)
 - GitHub


#### Procedure

 - Every Pull Request should be code-reviewed before being merged.
 - When a developer is ready to have their Pull Request reviewed, they should add the label `review-needed` to the Pull Request.
 - Any developer can review another's Pull Request, but the responsibility for code-review falls to the Project Maintainer; and it is their responsibility to oversee the architecture and integrity of the project's codebase.
 - When reviewing a Pull Request, your goals should be:
     - to spot bugs
     - to evaluate whether the Pull Request would be [hot compatible](developing_features/hot_compatibility.md) or not
     - to understand the intention of the code
     - to see whether the code's style, architecture, or idioms fits with the conventions of the rest of the codebase
     - to make recommendations if the code could communicate more clearly or structured more cleanly
 - After reviewing a Pull Request, remove the `review-needed` label and add:
     - `review-pass` if the Pull Request can be deployed with no further work
     - `review-pass` + `suggestions` if the Pull Request is OK to be deployed, but you've made suggestions for the committer to consider
     - `review-pass` + `hold` if the Pull Request is OK to be deployed, but it should be held until another Pull Request is merged — or until a scheduled maintenance window. (Add a comment explaining the conditions for the `hold`)
     - `review-hold` if you've asked questions that committer should answer or identified things that the committer should resolve before the Pull Request can be merged

#### Related Topics

 - [Creating a Pull Request](../developing_features/pull_requests.md)
