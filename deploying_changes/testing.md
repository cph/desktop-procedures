# [Deploying Changes](../deploying_changes.md) / Testing

#### Tools Used

 - Slack
 - [GitHub](https://github.com)

#### Procedures

 - First, developers check that their pull request needs to be tested by the testers (see "When to Test", below).
 - We ensure that we've written full testing instructions on the main comment of the [pull request](../developing_features/pull_requests.md).
 - We deploy pull request to [staging](staging.md), and then request that a tester begin testing the newly-deployed pull request by asking, "Can I snag a tester?" in the #testers channel on Slack. (Since Slack added its teams feature, you can also ask to snag a `@testers`, which will notify everyone in the testers group).
 - Testers test the pull request, noting any issues, regressions, or suggestions they encounter in the main pull request comment (see below).
 - When testers have finished testing a pull request, they will apply the appropriate labels (see below) to indicate the state of the pull request to the developers.
 - If any issues need to be addressed, the developers may repeat the process after making changes that necessitate additional testing.

###### When to Test

The normal procedure is to have all pull requests tested by the testers. However, a pull request may be labeled `no-test` instead of `test-needed` when:
 - it is either difficult or impossible for the Testers to set up the conditions to verify the change
 - the change is easily verified in code review (e.g. It's easy to verify a spelling change by reading the code)
 - the pull request resolves an urgent problem in Production where the pull request could not make the situation _worse_.

###### Tester Findings

- As testers test a pull request, they will interact with the testing instructions section of the main comment on the pull request on GitHub.
  - As items pass testing, testers will check the checkbox next to that feature.
  - If an item fails testing, testers will add a thumbs-down (`:-1:`) emoji after the checkbox to indicate that they _have_ tested it, but it failed.
  - Testers are encouraged to add additional comments to a failing item, indicating how it failed and what special procedures, if any, caused the failure.
- When, in the course of testing a pull request, a tester encounters an issue with the feature being tested or a regression caused by that feature, they will record their findings in a new section on the main comment of the pull request. It will ordinarily be divided by a horizontal rule from the testing instructions and have a new header of "Test Findings".
  - The findings listed in this new section should be preceded by checkboxes so that, once addressed, they can be checked off by the tester as with the checkboxes under the testing instructions.
  - Descriptions of the issues encountered should be as descriptive as possible, indicating the encountered behavior, as well as steps to reproduce that behavior. Screenshots and/or `.gifs` of the issue may also be included to help the developers diagnose the problem.
  - Once a developer has addressed a test finding, they may place a `:star:` or `:star2:` emoji at the beginning of the description to indicate to the testers that the issue has been addressed.
- Occasionally, an issue will be found in testing that was not introduced by the pull request (i.e., it also exists on production). In this case, the tester should create a separate Alert for the bug rather than tying it to the pull request.

###### Suggestions

- If a tester encounters behavior that is slightly confusing or could be improved, but is not significant enough to warrant a hold, they may create in the main comment of the pull request a new section titled "Suggestions".
- Findings in this section should generally follow the same formatting and procedure as Test Findings above, while also allowing for more general comments preceded by a bullet instead of a checkbox.

###### Testing-Related Labels in GitHub

 - `on-staging` - add after deploying to staging if it's not automatically added by Houston.
 - `test-needed` - add when the pull request is ready for testing and/or more testing; remove when testing is done.
 - `test-pass` - add when the pull request has passed testing with no show-stopping issues or regressions.
 - `test-hold` - add when the pull request has show-stopping issues or regressions; remove when they've been addressed.
 - `suggestions` - add when there are minor issues or ways the pull request could be tweaked to be better for customers. (**NB:** The `suggestions` label can also be used in conjunction with [code review](code_review.md).)
 - `no-test` - add when the pull request cannot be reasonably tested; use sparingly.

#### Related Topics

 - [Creating a Pull Request](../developing_features/pull_requests.md)
 - [Deploying to Staging](staging.md)
 - [Complete List of Pull Request Labels](../reference/labels.md)

