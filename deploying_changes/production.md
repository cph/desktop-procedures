# [Deploying Changes](../deploying_changes.md) / Deploying to Production

#### Tools Used

 - GitHub
 - `ep deploy`
 - `ep release`


#### Procedure

 - Project Maintainers regularly merge pull requests that have passed testing (or don't require testing) and have passed code review, and deploy them to Production.
     - Branches are merged using the "Merge" button on the Pull Request in GitHub
     - The `main` branch is deployed using `ep deploy production`
     - The deploy is recorded using `ep release` to generate a release with release notes in GitHub
 - In general, deploys to Production should take place frequently; but there are two kinds of pull requests that cannot be deployed immediately:
     1. PRs that are not ["Hot Compatible"](developing_features/hot_compatibility.md) (i.e. that require a maintenance page)
     2. PRs that introduce new UI (i.e. that should be released in conjunction with marketing and/or documentation)
 - For apps that frequently have long-running background jobs (e.g., data imports), the Project Maintainer should check with the support team before deploying to Production.
 - When it is necessary to use a maintenance page during a deploy, the deploy should be planned with the support team and the product's marketer. This way, we can inform customers about the upcoming downtime.
 - When a Pull Request would introduce new UI (and if the marketing team or the support team is interested in announcing releases or updating documentation), the deploy should be scheduled with the marketing and/or support teams.
     - Note: when we have a `beta` environment for a product, new features can be deployed immediately to the `beta` environment and merged from there to `main` at the regular time.
     - The `beta` branch is deployed using `ep deploy beta`


#### Related Topics

 - [Code Review](../deploying_changes/code_review.md)
 - [Deploying to Staging](../deploying_changes/staging.md)
 - ["Hot Compatibility"](../developing_features/hot_compatibility.md)
