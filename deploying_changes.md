# Deploying Changes


#### Rationale

We want to get new features and fixes into customer's hands as quickly as possible. We also _don't_ want features and fixes to stack up because [large batch sizes can slow us down](https://yow.eventer.com/yow-2012-1012/the-practical-science-of-batch-size-by-don-reinertsen-1269). If we are to deploy frequently, we need (all the more) for deploys to be fast and to be free of adverse side-effects.

Meanwhile, other teams have processes (like updating documentation or announcing releases) that need to be tied to certain deploys, and those efforts should be synchronized.


#### Goals

These processes should ensure:
  1. that regressions are minimized
  2. that deploying is resilient and reliable
  3. that deploying is inexpensive (so that deploys can be done frequently)
  4. that colleagues are informed of releases


#### Procedures

 - We write code that is ["Hot Compatible"](hot_compatibility.md) so that deploys have as little impact on running software as possible.
 - Developers [work on topic branches](git_flow.md) and [create Pull Requests](pull_requests.md) so that we can track changes and deploy them independently of each other.
 - Another developer (usually the Project Maintainer) [reviews the Pull Request](code_review.md). Code Review helps to disseminate insights, prevent regressions, and improve the quality of the codebase.
 - We [deploy Pull Requests to staging](deploying_changes/staging.md) and ["snag a tester"](testing.md) when they require testing.
 - Project Maintainers regularly merge Pull Requests that have passed testing and review, and [deploy them to Production](deploying_changes/production.md).


#### Related Topics

 - [Planning Releases](planning_release.md)
 - [Operating Applications](operating_applications.md)
