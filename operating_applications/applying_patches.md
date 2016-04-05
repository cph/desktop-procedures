# [Operating Applications](../operating_applications.md) / Applying Patches


#### Rationale

EngineYard publishes patches for its VMs regularly. Many of these are in response to CVEs and all of them _should_ be applicable to a VM seamlessly.


#### Procedure

 - Every Monday morning, Maintainers will check EngineYard for new patches. If there are any, they'll upgrade our _Staging_ VMs at that time and watch for problems.
 - Every Tuesday evening, if any changes were applied to _Staging_ VMs on Monday, the same patches will be applied to our _Production_ VMs.
 - If patches can't be applied seamlessly or require a restart, a maintenance screen should be shown during the process and the application of patches should be planned with the support team and the product's marketer. This way, we can inform customers about the upcoming downtime.


#### Related Topics

 - [Deploying Changes](deploying_changes.md)
