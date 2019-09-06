# [Developing Features](../developing_features.md) / Guides / Setting Up a New Project


#### Checklist

###### For a Public project

 - Generate a new gem with `bundle gem abc`
 - Commit it, before changing anything, as `[skip] Initial commit from Bundler 1.16.1 (1m)` (giving the appropriate version of Bundler)
 - [Create a new repo on GitHub](https://github.com/new) (e.g. `cph/abc`)
 - [Enable branch protection](https://help.github.com/articles/configuring-protected-branches/) on `master` and turn on these settings:
    - Require pull request reviews before merging
    - Require status checks to pass before merging
       - Require branches to be up to date before merging
       - Select Travis CI - Pull Request
       > You won't be able to do this until you've pushed commits and had one build run on Travis.

###### For a Private project

 - Generate a new Rails project with `rails new xyz`
 - Commit it, before changing anything, as `[skip] Initial commit from Rails 5.2.2 (1m)` (giving the appropriate version of Rails)
 - [Create a new repo on GitHub](https://github.com/new) (e.g. `cph/xyz`)
    - Configure **Collaborators and Teams**
       - **Developers** have **Write** access.
       - **Houston** has **Admin** access.
       - **Designers** have **Write** access.
       - **Testers** have **Write** access.
 - [Create a new app on Errbit](https://errbit.cphepdev.com/apps/new) (You may have to log out and log back in as an Admin)
     - Fill in **GitHub Repo** (`cph/xyz`) so that lines in the backtraces can be linked to source
     - Under **Watchers**, add the non-admin users in Errbit
     - Under **Notification Service**, pick **Webhook** and fill in the URL `https://houst.in/projects/xyz/hooks/exception_report`
 - Create a new project in Houston [for the appropriate Team](https://houst.in/)
     - Give it the same slug as its GitHub repo
     - Set **Version Control** to **Git** and fill in the the URL `git@github.com:cph/xys.git`
     - Set **Error Tracker** to **Errbit** and fill in the AppId (from the URL `https://errbit.cphepdev.com/apps/:app_id`)
     - Set **CI Server** to **Jenkins**
     - Set **Ticket Tracker** to **Houston**
     - Enable these features:
        - **Feedback** (i.e. https://houst.in/feedback/by_project/xyz)
        - **Goals** (so the new project can be added to Roadmaps)
        - **Releases** (so that you can create release notes for the project)
 - [Create a new job in Jenkins](https://ci.cphepdev.com/view/all/newJob)
     - Give it the same name as its slug in Houston
     - Copy its configuration from an existing job (e.g. **lsb**)
     - Change **Respository URL** to the URL `git@github.com:cph/xys.git`
     - Update the Rails project for Jenkins:
        - Start by using the `ep jenkins:config` command in the EP Toolchain; it will generate/modify the files needed for running the tests on Jenkins.
        - The generated `bin/cibuild` script is what Jenkins will use to run the tests
        - You may need to add instructions to the `cibuild` script to copy in any relevant config files before the tests are able to run.
 - [Enable branch protection](https://help.github.com/articles/configuring-protected-branches/) on `master` and turn on these settings:
    - Require pull request reviews before merging
    - Require status checks to pass before merging
       - Require branches to be up to date before merging
       - Select jenkins
       > You won't be able to do this until you've pushed commits and had one build run on Jenkins whose status Houston has reported to GitHub.
 - Add the appropriate Slack channels: `#xyz`, `#xyz-support`, `#xyz-incubation`
