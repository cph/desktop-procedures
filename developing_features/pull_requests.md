# [Developing Features](../developing_features.md) / Creating a Pull Request

#### Rationale

Pull requests are the central hub for feature development. They allow for easy tracking of the state of a feature through testing and code review via labels applied to pull requests. They facilitate Houston running automatic tests and checks on the code before merging and deploying. They provide a place where developers, reviewers, and testers can communicate with each other about the feature in order to make it the best it can be before incorporating it into the main project. Most of this functionality is granted by default from GitHub, but we have also added a handful of conventions to better work with out processes.

#### Tools Used

 - [GitHub](https://github.com)

#### Goals

These procedures should ensure:

 - that features are able to be easily tested and code-reviewed
 - that the state of features are centrally tracked
 - that automatic checks are able to run before merging and deploying a feature

#### Procedures

 - As soon as is feasible, [push](git_flow.md) your topic branch up to `origin` and create a pull request; branches without an associated pull request will be pruned weekly by Houston.
 - Creating a pull request is often as easy as visiting the project page on GitHub, which will detect recent pushes and prompt you to create a pull request for any recently-pushed branch that doesn't yet have an associated pull request. Otherwise, you can click the "Create pull request" button under the "Code" tab.
 - Ensure you are requesting your branch be merged into the correct base. Whichever base you branched off of when creating your branch should be the base to which you're comparing when creating a pull request. If you accidentally choose the wrong base, you must close the pull request and re-create it using the correct base.
 - Ordinarily, you should _only_ base your pull request off of `master` or (if the project has a beta environment) `beta`. We do not base pull requests off other topic branches.
 - Use a helpful name for your pull request so that developers and testers can tell at a glance the nature of the feature covered by the pull request.
 - Apply the appropriate labels to your pull request depending on the state of your feature (see below).
 - Before testing the feature, make sure to write testing instructions (see below) in the main comment; this is ordinarily done _before_ [deploying to staging](../deploying_changes/staging.md).
 - If for some reason you need to close your pull request (e.g., it's been incorporated into another topic branch), be sure to reference any related pull requests in a comment using the pound sign followed by the other pull request's number. E.g., `Closed in favor of #1234`

###### Applying Labels

Labels communicate various aspects of the state of a pull request in our process. See the [Labels](../reference/labels.md) page for a full reference.

 - Pick `feature` if the pull request is a normal part of the milestone; pick `hotfix` if the pull request should be merged and deployed directly to production as soon as possible.
 - Pick `test-needed` unless the pull request can't reasonably be tested by the testers; in that case, pick `no-test`.
 - Add `review-needed` unless it's a work-in-progress (`wip`).

###### Writing Testing Instructions

 - In preparation for putting a pull request through testing, we make sure to write testing instructions in the first / main comment on a pull request.
 - These instructions are written in GitHub-flavored Markdown and ordinarily contain at least three elements: a heading, any necessary background information, and sets of checkboxes indicating things to test.
 - The heading is usually no more than "Testing Instructions" set at heading level 3 or lower. This helps set apart these instructions from any other information included in the pull request.
 - Background information is also often included. This could be anything that would help the testers in understanding the changes made or in testing the correct aspects of the application. If a pull request affects only a single view or addresses a specific alert, that information is useful to put in this section.
 - The checkboxes (`- [ ]` in GitHub-flavored markdown) of items to test are the main thing in the testing instructions. They indicate the desired outcomes from interacting with various bits of the application. As such, they should be as clear and specific as possible, while yet describing the outcomes and procedures in terms of how a user of the application would interact with it.
   - E.g., When checking a calendar in the calendars dropdown, the events that belong to those calendars should become visible in the view.
 - Depending on the nature of what's being tested, checkboxes may be broken down and grouped so that testers can easily check off different aspects of the same feature working. E.g., You wish to test a feature on multiple browsers, and so you have a regular bullet point for the feature, and then a checkbox for each browser nested underneath.

#### Related Topics
 - [Code Review](../deploying_changes/code_review.md)
 - [Testing](../deploying_changes/testing.md)
