# [Developing Features](../developing_features.md) / Sprint Planning

#### Rationale

By dividing milestones into weekly "sprints", we seek to better get a handle on the individual tasks that go into accomplishing a milestone. Sprints help us to better estimate how much work is involved in a milestone, as well as providing regular opportunity for feedback and evaluation of milestone progress. Though the cycle of planning a sprint before starting and evaluating the sprint upon its conclusion, we improve our ability to estimate the work involved in tasks, as well as our own ability to complete the work, which leads in turn to better planning and communication at the milestone level. Sprints give us a tight feedback loop without being paralyzingly granular.

#### Goals

These procedures should ensure:

 - that the team sets realistic goals for completing tasks in the current milestone
 - that obstacles and difficulties are anticipated and accounted for
 - that the team is better able to offer feedback on milestone progress during [incubation meetings](../planning_releases/incubation.md)

#### Tools Used

 - [The Sprint view](https://houst.in/sprints/current) (Houston)
 - [Project Roadmaps](https://houst.in/roadmaps) (Houston)
 - `ted` (`ep tasks edit` in [The EP Toolchain](https://github.com/cph/ep))

#### Procedures

###### Beginning-of-Milestone
 - At the beginning of a new milestone, the project team will meet for an extended period to divide the milestone into tasks and get an idea of the flow of the work.
 - Using Houston's [Project Roadmaps](https://houst.in/roadmaps) page, the team will enter the tickets for the milestone. Tickets should be worded as user stories, e.g., "I should be able to use X to accomplish Y."
 - Optionally, the team may wish to further discuss and break down tickets into smaller tasks, even if not all of the tasks will be part of the next sprint (see below).

###### Weekly Sprint

 - Product teams meet either at the end of the week or the beginning of the week to plan the next sprint based on the outcomes of weekly [incubation meetings](../planning_releases/incubation.md).
 - If not already done, the team will discuss the implementation of the milestone's tickets, dividing them into tasks using `ted <ticket-number>` or `ep tasks edit <ticket-number>` in a terminal in the project's root directory.
 - The first task is always auto-populated by Houston to be the ticket description. The team should change this to be the actual first task that will go towards completing the ticket.
 - The team adds tasks as necessary.
 - The team also estimates the amount of effort required to complete each task. Generally, this number will correspond to the number of hours required to complete the task, rounded to one decimal place.
 - Once tasks have been added/edited, estimated, and saved, each member of the team will navigate to the [Sprint View](https://houst.in/sprints/current) of Houston and use the text field to add the tasks they wish to take on to the sprint. By default, any tasks you add will be also checked out by you.
 - As you complete tasks throughout the week, be sure to tag the full task number as part of the commit message as outlined in our [style guides](https://github.com/cph/style-guides) so that Houston can automatically mark the tasks as complete. To make sure you're using the correct format, you can copy the tag from the task on the [Sprint View](https://houst.in/sprints/current). (You can also manually mark the task as complete on the [Sprint View](https://houst.in/sprints/current).)

#### Related Topics

  - [Planning Releases](planning_releases.md)
