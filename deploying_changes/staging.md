# [Deploying Changes](../deploying_changes.md) / Deploying to Staging


#### Tools Used

 - Slack
 - Houston
 - `ep deploy` from [The EP Toolchain](https://github.com/cph/ep)


#### Procedure

 - Before deploying, check if another pull request is on Staging and in active testing.
  
   You can see what's on Staging by looking at the [GitHub](https://github.com/search?q=org%3Acph+is%3Apr+label%3Aon-staging%2Con-staging2+is%3Aopen&type=pullrequests). If you're using `ep deploy`, it will check for you.

 - Deploying with `ep deploy`
   
   In a terminal window, on the branch you want to deploy, type `ep deploy`. You can also manually specify a branch name (helpful when using `jj`) by running `ep deploy --branch=branch-name`.

 - Deploying using environment-specific commands **(not recommended)**

   You can also deploy directly to Heroku using `git push`. If you deploy directly like this, not all automations may trigger to notify about the deploy.


#### Related Topics

 - [Testing](testing.md)
