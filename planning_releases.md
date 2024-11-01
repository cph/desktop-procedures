# Planning Releases


#### Rationale

Product Development is an activity that generates information. Efforts to implement a domain yield new insights into that domain. Releases in response to feedback elicit new feedback. Customers' needs, our understanding of their needs, markets, and technical possibilities all constantly change. All these changes affect the payoff of a plan, meaning that the optimal path forward is always a moving target.

At the same time, the _process of planning_ is our first opportunity to anticipate research and design needs or architectural constraints. And plans themselves allow us to synchronize work with other teams like Marketing and Support.

###### Conclusion

Our planning process should be characterized by transparency, [late-binding](reference/late_binding.md), and progressive definition.


#### Goals

Our planning process should maximize:

 1. Our access to information about our customers
 2. Our ability to change plans in response to new information
 3. The visibility of our plans and transparency of our planning


#### Procedures

 - We gather feedback from our customers through Sales, Support, and research into one place where it can be categorized and searched.
 - Product Teams meet quarterly for [Roadmapping](planning_releases/roadmapping.md). These longer meetings allow them to review feedback and revise goals for upcoming quarters.
 - Product Teams with active roadmaps discuss questions that arise during development asynchronously via either the `#ep-incubation` channel in Slack or -- for longer discussions -- via [GitHub Discussions](https://github.com/orgs/cph/discussions). Having as much conversation as possible this way both keeps our weekly meetings focused and naturally documents discussions and decisions made.
 - Product Teams with active roadmaps also meet weekly for [Incubation](planning_releases/incubation.md). These meetings allow teams to check in regularly and facilitate real-time refinement of milestones.
 - When Product Teams identify gaps in their understanding of customers, the Product Designer and UX Team conduct research to fill them.
 - Ahead of upcoming cycles, Product Designers shape goals into a more concrete Proposal that outlines the work to be done, including how the feature or changes should look and behave.
 - Before the cycle starts, Product Teams place shaped Proposals onto the Roadmap and commit to working on those features during the cycle. Unshaped work **is not placed on the Roadmap**.
 - At the start of a milestone, developers [break User Stories into specific tasks](developing_features/task_slicing.md).


#### Tools

- Houston Feedback
- [Jira](https://concordiapublishing.atlassian.net/jira/software/projects/EP/boards/5/timeline)
- [Roadmap Visualization](http://ep-grand-central.herokuapp.com/dashboards/roadmap)
- [GitHub Discussions](https://github.com/orgs/cph/discussions)


#### Related Topics

 - [Designing Products](designing_products.md)
 - [Developing Features](developing_features.md)
 - [Resolving Alerts](resolving_alerts.md)
