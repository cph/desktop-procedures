# [Reference](../reference.md) / Labels

Labels communicate various aspects of the state of a pull request.

#### Added by Developers

See also [Testing](../deploying_changes/testing.md) and [Code Review](../deploying_changes/code_review.md).

 - `wip` stands for "work-in-progress" and indicates the feature covered by the pull request is incomplete and thus should not yet be looked at for testing or code review.
 - `experimental` indicates the feature is incomplete with respect to its design, if not also its implementation. This is often used for "spikes" where developers will try to see how far they can get on building a feature without following normal, [test-driven development](test_driven_development.md). This label should be used sparingly.
 - `feature` indicates that this feature is part of the regular roadmapping process and—if available—will be merged and deployed to the `beta` environment _first_ before going out to the production environment. Opposite of `hotfix`.
 - `hotfix` indicates that this feature either addresses an issue which is currently a problem in production or, for whatever reason (e.g., it's not [hot-compatible](hot_compatibility.md)) it cannot be deployed to `beta` first and should instead be directly merged into `master` and deployed directly to the production environment. Opposite of `feature`.
 - `no-test` indicates that this feature either cannot be tested by the testers or is insignificant enough that it need not be tested. This label should be used sparingly.
 - `test-needed` indicates a pull request is ready for and in need of testing.
 - `review-needed` indicates a pull request is ready for and in need of code review.
 - `hold` indicates that some other condition needs to be fulfilled before this pull request is merged and deployed. Most often this label is used when rolling out multiple, sequential changes to facilitate [hot compatibility](hot_compatibility.md).

#### Added by Reviewers

See also [Code Review](../deploying_changes/code_review.md).

 - `review-pass` indicates that the reviewer has found the code ready to be merged into the base branch.
 - `review-hold` indicates that the reviewer has found issues with or has questions about the code that should be addressed before it's merged into the base branch.
 - `suggestions` is often used in conjunction with the `review-pass` label to indicate the presence of issues or questions that should not necessarily prevent the code from being merged, but which the developer may yet want to address.

#### Added by Testers

See also [Testing](../deploying_changes/testing.md).

 - `test-pass` indicates that the tester has found the new feature works as expected and did not introduce any regressions.
 - `test-hold` indicates that the tester has found either that the new feature does not completely work as expected or has introduced regressions.
 - `suggestions` is often used in conjunction with `test-pass` to indicate the presence of issues or questions that should not necessarily prevent the code from being merged, but which the developer may yet want to address.

#### Added by Houston

 - `on-staging` indicates that a pull request is currently deployed to staging. It is up to the developer to remove this label once testing of the pull request is concluded.
