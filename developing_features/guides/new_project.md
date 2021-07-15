# [Developing Features](../developing_features.md) / Guides / Setting Up a New Project


#### Checklist

###### For a Public project

 - Generate a new gem with `bundle gem abc`
 - Commit it, before changing anything, as `[skip] Initial commit from Bundler 2.1.0 (1m)` (giving the appropriate version of Bundler)
 - [Create a new repo on GitHub](https://github.com/new) (e.g. `cph/abc`)
 - [Enable branch protection](https://help.github.com/articles/configuring-protected-branches/) on `master` and turn on these settings:
    - Require pull request reviews before merging
    - Require status checks to pass before merging
       - Require branches to be up to date before merging
       - Require checks automatically run by GitHub Actions to pass before merging
       > You won't be able to do this until you've pushed commits and had one run of your GHA checks.

###### For a Private project

 - Generate a new Rails project with `rails new xyz`
 - Commit it, before changing anything, as `[skip] Initial commit from Rails 6.1.0 (1m)` (giving the appropriate version of Rails)
 - [Create a new repo on GitHub](https://github.com/new) (e.g. `cph/xyz`)
    - Configure **Collaborators and Teams**
       - **Developers** have **Write** access.
       - **Houston** has **Admin** access.
       - **Designers** have **Write** access.
       - **Testers** have **Write** access.
 - [Create a new app on Sentry](https://sentry.io) (You may have to log out and log back in as an Admin)
     - Link it to the repo on GitHub
     - Add the project short name to the project/repo map in the `ep-sentry-sync` lambda in the EP Toolchain and re-deploy the lambda using `ep lambda:deploy ep-sentry-sync`
 - Create a new project in Houston [for the appropriate Team](https://houst.in/)
     - Give it the same slug as its GitHub repo
     - Set **Version Control** to **Git** and fill in the the URL `git@github.com:cph/xys.git`
     - Set **Error Tracker** to **None** (error tracking will happen in GitHub)
     - Set **CI Server** to **None** (CI should be set up to run in GitHub with a GitHub Action workflow)
     - Set **Ticket Tracker** to **Houston**
     - Enable these features:
        - **Feedback** (i.e. https://houst.in/feedback/by_project/xyz)
        - **Goals** (so the new project can be added to Roadmaps)
        - **Releases** (so that you can create release notes for the project)
 - [Enable branch protection](https://help.github.com/articles/configuring-protected-branches/) on `master` and turn on these settings:
    - Require pull request reviews before merging
    - Require status checks to pass before merging
       - Require branches to be up to date before merging
       - Require checks automatically run by GitHub Actions to pass before merging
       > You won't be able to do this until you've pushed commits and had one run of your GHA checks.
 - Add the appropriate Slack channels: `#xyz`, `#xyz-support`, `#xyz-incubation`
