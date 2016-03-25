# [Deploying Changes](../deploying_changes.md) / Deploying to Staging


#### Tools Used

 - Slack
 - Houston
 - `ep deploy` from [The EP Toolchain](https://github.com/cph/ep)


#### Procedure

 - Before deploying, check if another pull request is on Staging and in active testing.
  
   You can see what's on Staging by looking at the [Staging Dashboard](http://houst.in/dashboards/staging), by using the `/staging` command in Slack, or by asking Houston `what's on staging?`. If you are using Slack to deploy your pull request (see below), Houston will check for you.

 - Deploying via Slack **(recommended)**
   
   Ask Houston to deploy the pull request. You can indicate the pull request either by the branch name or by the pull request number. E.g., `Houston, deploy feature-branch` or `@houston, deploy 1234`.

 - Deploying with `ep deploy`
   
   In a terminal window, on the branch you want to deploy, type `ep deploy`

 - Deploying using environment-specific commands **(not recommended)**

   You can also deploy directly to EngineYard or Heroku using `ey deploy` or `git push`. If you deploy using one of these methods, you should also run `ep deploy:record` afterwards to inform Houston of the deploy.


#### Related Topics

 - [Testing](testing.md)
