# [Deploying Changes](../deploying_changes.md) / Deploying to Staging


#### Tools Used

 - Slack
 - Houston
 - `ep deploy` from [The EP Toolchain](https://github.com/cph/ep)


#### Procedure

 - Before deploying, check if another pull request is on Staging and in active testing.
  
   You can see what's on Staging by looking at the [Staging Dashboard](http://houst.in/dashboards/staging), by using the `/staging` command in Slack, or by asking Houston `what's on staging?`. If you are using Slack to deploy your pull request (see below), Houston will check for you.

 - Deploying with `ep deploy`
   
   In a terminal window, on the branch you want to deploy, type `ep deploy`

 - Deploying using environment-specific commands **(not recommended)**

   You can also deploy directly to Heroku using `git push`. If you deploy directly like this, not all automations may trigger to notify about the deploy.


#### Related Topics

 - [Testing](testing.md)
