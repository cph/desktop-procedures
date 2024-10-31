# [Developing Features](../developing_features.md) / Creating a Pull Request

#### Goals

We create a pull request for every change in order to:

 - allow every change to be [code-reviewed](../deploying_changes/code_review.md)
 - track, in one place, the actions that need to be taken to get it merged

#### Procedures

 - Work on [topic branches](git_flow.md)
 - Push your work to [GitHub](https://github.com) (`git push origin <branch-name>`) and create a pull request against `main`*
   > \* When a project has a beta environment, we've also had a branch off of `main` named `beta`. In this case, hotfixes are always based off `main` and new features are based off of `beta`.
 - Add the `review-needed` label to every pull request
   > Sometimes a pull request isn't ready for review immediately. In this case, add the `wip` label instead of the `review-needed` label until the PR _is_ ready to be reviewed.
 - Add the `hotfix` label to every pull request that resolves an Alert
 - Add the `no-test` label to a pull request that doesn't need to be tested on Staging.
   > This is less common, but a pull request doesn't need to be human-tested  when it's easy to verify by a reviewer or is well-covered by automated tests.
 - If not adding the `no-test` label, add the label `test-needed` and write **Testing Instructions**
   > ##### Example:
   >     ## Testing Instructions
   >  
   >     - [ ] if I change a hymn's category, I find it when I search
   >           for the new category and not the old one
   >     - [ ] if I change a hymn stanza's related scripture, I find
   >           the hymn when I search for the new reading and not the
   >           old one (and I still find the hymn by the related
   >           scripture of its other stanzas)

#### Related Topics

 - [Committing Work](git_flow.md)
 - [Code Review](../deploying_changes/code_review.md)
 - [Testing](../deploying_changes/testing.md)
 - [Merging Pull Requests](../deploying_changes/production.md)
