# [Deploying Changes](../deploying_changes.md) / Deploying to Production

#### Tools Used

 - `ep merge`
 - `ep deploy`


#### Procedure

 - Project Maintainers regularly merge pull requests that have passed testing (or don't require testing) and have passed code review, and deploy them to Production.
     - Branches are merged using `ep merge <branch-name>`
     - The `master` branch is deployed using `ep deploy production`
 - In general, deploys to Production should take place frequently; but there are two kinds of pull requests that cannot be deployed immediately:
     1. PRs that not ["Hot Compatible"](developing_features/hot_compatibility.md) (i.e. that require a maintenance page)
     2. PRs that introduce new UI (i.e. that should be released in conjunction with marketing and/or documentation)
 - When it is necessary to use a maintenance page during a deploy, the deploy should be planned with the support team and the product's marketer. This way, we can inform customers about the upcoming downtime.
 - When a Pull Request would introduce new UI (and if the marketing team or the support team is interested in announcing releases or updating documentation), the deploy should be scheduled with the marketing and/or support teams.
     - Note: when we have a `beta` environment for a product, new features can be deployed immediately to the `beta` environment and merged from there to `master` at the regular time.
     - The `beta` branch is deployed using `ep deploy beta`


#### Related Topics

 - [Code Review](../deploying_changes/code_review.md)
 - [Deploying to Staging](../deploying_changes/staging.md)
 - ["Hot Compatibility"](../developing_features/hot_compatibility.md)
