# Operating Applications


#### Rationale

We want our products to be reliable, secure, and performant. These qualities start with decisions about our platform; but expertise at Web Server configuration, VM maintenance, and database administration are not among our core competencies. Therefore, we will select services that encapsulate that expertise and tools to help us monitor and respond to relability, security, or performance problems with our applications.


#### Services

Presently, we use:

 - Route53 to host our DNS records
 - S3 to host static assets
 - Heroku to host our Postgres databases
     - the company is very active in Postgres development: they are experts
 - Mailgun to deliver emails
 - EngineYard to host VMs for running our applications
     - it runs on AWS and so does Heroku Postgres so there is lower latency between VMs and databases
     - it specializes in Rails hosting and support
 - Heroku to host lighter-weight applications

and for monitoring:

 - Alertra for reliability
 - Skylight for performance
 - BeyondTrust for security


#### Procedures

 - We design applications to serve static assets from S3 rather than from the application's server. This is more cost-effective and performant.
 - We require our application servers to support hot restarts (as Heroku and Unicorn do) so that our deploys don't impact our customers' experience. This allows us to deploy more frequently which, in turn, reduces batch sizes and cylce time.
 - Project Maintainers receive text messages from Alertra whenever a project they maintain is down. This allows them to respond to downtime as soon as they are able.
 - When an application requires additional software to be installed on its production server, we add that software through a scripted mechanism (cloud recipes on EngineYard and buildpacks on Heroku). This makes that bit of configuration applicable to new VMs, which makes our infrastrure more easily scalable.
 - We [apply patches](operating_applications/applying_patches.md) to our VMs regularly.



#### Related Topics

 - [Deploying Changes](deploying_changes.md)
