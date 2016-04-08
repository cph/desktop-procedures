# [Developing Features](../developing_features.md) / Git Flow

#### Goals

These processes should make it as easy as possible:

 1. for multiple developers to collaborate on a project
 2. to deploy (and to roll back deploys)
 3. to get insights from Git about when and why a change was made to the codebase


#### Tools Used

 - [Git](https://git-scm.com)
 - [GitHub](https://github.com)
 - `ep who`
 - `ep pair` / `ep unpair`
 - `ep respawn`
 - `ep merge`

#### Procedures

###### Branching

 - Always work on topic branches. If you are working on a feature in the regular roadmap (and if the project has a `beta` branch), create your topic branch off of `beta`. If you are working on an alert (or if the project doens't have a `beta` branch), you should branch off of `master`.
 - Before branching, make sure your local copy of either the `master` or `beta` branch is up-to-date with the `origin` by fetching and using `git pull` to fast-forward. Sometimes, the `beta` branch will not be able to be fast-forwarded. In this case, you may wish to use `ep respawn beta` in order to pull a fresh copy of the `beta` branch down from the remote server.
 - Branch names are typically lower-case, with words separated by dashes. Names should balance being succinct, yet descriptive.

###### Committing

 - Commits should be as small as possible while maintaining the code in a workable state. We try not to commit code when the project is in a broken state.
 - When committing, we strive to minimize "commit noise", i.e., changes that don't affect the code or state of the project, especially whitespace changes.
 - You may wish to double-check as whom you're committing using `ep who`. If you are pairing with someone, use `ep pair` to change your git identity to the combined identities of those pairing. E.g., `ep pair matt bob chase ben` would combine those four git identities into one. Use `ep unpair` to go back to committing as only yourself.
 - Be sure to follow our [Style Guide](https://github.com/cph/style-guides) for commits.


###### Pushing

 - Push your branch to GitHub regularly.
 - _**Always**_ double-check that you will not be overwriting other work before forcing a push!
 - When you push your changes, if a pull request does not yet exist for the branch, [create a Pull Request](pull_requests.md) for your branch. (Note: Houston will prune remote branches without an open pull request on a weekly basis.)

###### Merging

 - Ordinarily, combining related topic branches is accomplished via rebasing. Incorporating topic branches back into their base branch (`master` or `beta`) is accomplished via merging.
 - To merge two branches, switch to the branch _into which_ you wish to merge your topic branch. Then, use `ep merge topic-branch-name` to merge the two branches.
 - `ep merge` will automatically attempt to rebase your topic branch on the base branch before merging the two.
 - We usually leave the default merge message (e.g., "Merged branch 'topic-branch-name'") when merging back into the main branch.

###### Rebasing

 - When combining related topic branches or incorporating work added upstream (e.g., when branches are merged into either `master` or `beta` since you branched off), we ordinarily rebase.
 - We always do an interactive rebase; this allows us not only to edit and skip commits, but more fundamentally to check that the rebase will do what we're expecting it to do..
 - Occasionally we use rebasing to tweak past work. This is not ordinarily done (a new commit is usually best), but it can be used when fixing a small typo or error in a previous commit or when editing a migration.
 - After rebasing, when you go to push, you will almost certainly need the `-f` flag to force the push. _Always ensure you will not be overwriting other changes before forcing a push_ (See above)!

###### Squashing Commits

 - After a feature has been fully developed, we will squash the commits before merging into the base branch. This is usually done for larger features which are logically distinct, but are made up of many small commits.
 - Use interactive rebasing to squash commits into the smallest number of commits (usually 1 or 2) that make sense for the feature.
 - Make sure that the commit message of the commit into which the others are squashed is well-written and will be useful for release notes. The other commit messages (which Git puts by default into the description section of the target commit) may be discarded.

#### Related Topics
 
 - [Git documentation](https://git-scm.com/doc)
 - [Creating a Pull Request](pull_requests.md)
