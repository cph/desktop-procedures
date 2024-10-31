# [Developing Features](../developing_features.md) / Committing Work

#### Goals

These processes should make it as easy as possible:

 1. for multiple developers to collaborate on a project
 2. to deploy reliably and frequently
 3. to review each other's code
 4. to document our intention with commit messages


#### Tools Used

 - [Git](https://git-scm.com) or (optionally) [jj](https://github.com/martinvonz/jj)
 - [GitHub](https://github.com/cph)
 - `ep pair` (`ep unpair`, `ep who`)


#### Procedures

 - We work on topic branches so that we may [create pull requests](pull_requests.md) for every change.
   > - Never commit directly to `main`*
   > - Pull `main`* before creating a branch
   > - Rebase topic branches off of `main`* when `main`* changes
   >
   > <br> &#42; Newer projects default to using `main` as the default branch to match updated tooling. When a project has a beta environment, we've also had a branch off of <code>main</code> named <code>beta</code>. In this case, hotfixes are always based off <code>main</code> and new features are based off of <code>beta</code>.
 - We make our commits discrete, atomic, and succinct in order to better communicate their intention.
   > - Break separate logical changes into separate commits
   > - Don't commit partial work; no commit should knowingly leave the project in a broken state
   > - Minimize commit noise (changes that aren't relevant to the commit)
   >
   > <br> <h5>Rewriting Commits</h5> For a variety of reasons, we may not make discrete, atomic, and succinct commits <em>while working on a branch</em> — we may commit partial work, have a false start, or notice an oversight in a previous commit. We may then use tools like <code>git commit --amend</code>, <code>git rebase</code> and <code>git cherry-pick</code> to rewrite our branch's commits before requesting a review. Our goal is to make code review easier and git history more useful.
 - When pairing, we make commits jointly using `ep pair`
 - We [label commits](https://github.com/cph/style-guides#commits) to help Houston create release notes and resolve alerts automatically.
   > - Use `[feature]`, `[improvement]` and `[fix]` on changes that should be mentioned in release notes
   > - Use `[skip]` or `[refactor]` on changes that should not be mentioned in release notes
   > - Other labels like `[squash]` and `[wip]` may be useful for work-in-progress but should never be merged to `main`. (see <strong>Rewriting Commits</strong> above)
 - We [create a Pull Request](pull_requests.md) as soon as we are ready to [deploy our work to Staging](../deploying_changes/staging.md) for [Testing](../deploying_changes/testing.md), to request a [review](../deploying_changes/code_review.md), or to share our work-in-progress with other developers.


 #### Related Topics

  - [Style Guide for Commits](https://github.com/cph/style-guides#commits)
