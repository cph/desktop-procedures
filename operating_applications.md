# Operating Applications


#### Rationale

We want our products to be reliable, secure, and performant. These qualities start with decisions about our platform; but expertise at Web Server configuration, VM maintenance, and database administration are not among our core competencies. Therefore, we will select services that encapsulate that expertise and tools to help us monitor and respond to reliability, security, or performance problems with our applications.


#### Services

Presently, we use:

 - Route53 to host our DNS records
 - S3 to host static assets
 - Heroku to host our Postgres databases
     - the company is very active in Postgres development: they are experts
 - Mailgun to deliver emails
 - Heroku to host our applications
     - it already hosts our Postgres databases
     - its tools and buildpacks are actively maintained with recent versions of Ruby, Node.js, etc.
 - EngineYard to host VMs for legacy applications

and for monitoring:

 - Alertra for reliability
 - Skylight for performance
 - GitHub for vulnerabilities


#### Procedures

 - We design applications to serve static assets from S3 rather than from the application's server. This is more cost-effective and performant.
 - We require our application servers to support hot restarts (as Heroku and Unicorn do) so that our deploys don't impact our customers' experience. This allows us to deploy more frequently which, in turn, reduces batch sizes and cylce time.
 - Project Maintainers receive text messages from Alertra whenever a project they maintain is down. This allows them to respond to downtime as soon as they are able.
 - When an application requires additional software to be installed on its production server, we add that software through a scripted mechanism (buildpacks on Heroku and cloud recipes on EngineYard). This makes that bit of configuration applicable to new VMs, which makes our infrastructure more easily scalable.



#### Related Topics

 - [Deploying Changes](deploying_changes.md)
