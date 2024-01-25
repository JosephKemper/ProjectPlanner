## General Concepts

Build a console based task manager. For now, don't worry about building it as a graphical task manger. I can add that later. I have a lot to learn about building the front end side of things anyway. I want to start with an idea, this will have a name for the idea and a description. From there, once a project is attached to the idea, it will become a goal. Both projects and goals can have individual target dates set for them. Projects can then have tasks added to them. Ideas, goals, projects, and tasks can have notes added to them. 

I want the ability to display a goal and all of its attached projects, along with all of the related tasks. I also want the ability to see just the goals, projects, or tasks. I want to build an idea list, this will be a list of ideas that can eventually be turned into goals. All that needs to happen to turn an idea into a goal is to add a project to it. Goals, projects, and tasks will all have due dates, current status tracking, and the ability to add notes. Obviously, I will need the ability to create, edit, and delete goals, projects, and tasks. I want the task manager to automatically show a list of the next few tasks, projects, and goals that are due. It will also show any overdue goals, projects, or tasks that are overdue. 

I also want to add the ability to track requirements going both directions on both tasks and projects. For example, I want to be able to track if a certain project needs to be completed before another project can start, and have that be able to be tracked going both directions. Accordingly, I want to also put warnings built into projects and tasks letting you know if you are putting the project behind by not getting done on time. Taking it one step farther, I want to be able to attach to each project and task, the requirements that must be completed before hand, the estimated time to completion, and the project start date, and then have the tool give you a suggestion for how to organize the project to be able to complete it in as short of time as possible. I also want to be able to tell the project how many expected man hours it will take to complete each project/task, and how many are available for the duration of the project/task so that it can use that to better suggest the fastest route to completion. Accordingly, I think I want to be able to tell the program how many people I have, how many hours they work and what skills/projects/tasks they can work. I also want to track the needed resources for each project/task.

I want to be able to track the actual amount of time worked (via estimating the number of hours worked in a day not through actual reporting) on a project/task. I want to be able to get a projection based on time taken so far, for how long it will take to complete the project and compare that to the target completion date. And I want a progress report feature that could be used to report on progress for the day. 

## Features List

* Track ideas, goals, projects, and tasks (collectively referred to objects)
* Create, edit, delete goals, projects, and tasks
* Use current date to show objects by due date and flag any overdue objects
* Automatically show any overdue objects upon loading of the program
* Automatically show a list of any objects that are due soon
* Automatically convert an idea into a goal when a project is attached to it
* Display all objects attached to a goal
* Display all tasks attached to a project
* Display all tasks
* Display all projects
* Display all goals
* Attach due dates to any object other than an idea
* Track project/task requirements going both directions
* Track the number of people working on the project, the number of hours they work, and which tasks/projects they can work on. 
* Track the skills required for each project, and the skills each person has
* Use project/task requirements along with required skills and estimated hours to complete and then the skills and available hours for each project/task to create an suggested minimum completion time. 
* In project/task warnings letting them know if they are risking affecting the project completion target
* Track needed resources for each project/task
* Estimate the target completion date based on current progress. 
* Get and track progress reports for projects and tasks. 
* Track information about the people assigned to the project/task

## Feature Details
### Track ideas, goals, projects, and tasks
#### General Thoughts

Ideally, I will want ideas, goals, projects, and tasks to all be custom built data structures. 
Ideas:

* Name: Short and descriptive name for the idea.
* Description: Detailed description of the idea, including its purpose and potential benefits.
* Notes: Any additional information or thoughts about the idea.
* Priority: (Optional) A way to prioritize ideas for future development.
* Date created: (Optional) Timestamp of when the idea was created.

Goals:

* Inherit all data from the Idea class.
* Target date: Desired completion date for the goal.
* Projects: List of associated projects that contribute to achieving the goal.
* Status: Current progress status of the goal (e.g., in progress, on hold, achieved).
* Progress: The percentage of the goal that has been achieved.
* Start Date: The date when work towards this goal begins.
* Due Date: The target date for achieving this goal.

Projects:

* Inherit all data from the Goal class.
* Tasks: List of tasks required to complete the project.
* Resources: List of resources needed for the project (e.g., equipment, software, data).
* Skills: List of skills required for project completion.
* Team: List of individuals assigned to the project.
* Estimated time: Total estimated time required to complete the project.
* Start date: Planned start date for the project.
* Dependencies: List of other projects that need to be completed before this project can start (and vice versa).
* Risk assessment: (Optional) Potential risks associated with the project and mitigation strategies.
* Warnings: Alerts if the project is at risk of not meeting its target completion date.

Tasks:

* Inherit all data from the Project class.
* Supplies: List of specific supplies needed to complete the task.
* Estimated time: Estimated time required to complete the task.
* Actual Time Spent: The actual time spent on the task so far.
* Priority: Priority level within the project (e.g., high, medium, low).
* Status: Current progress status of the task (e.g., open, in progress, completed).
* Assigned to: Individual assigned to the task (optional).
* Dependencies: List of other tasks that need to be completed before this task can start (and vice versa).
* Warnings: Alerts if the project is at risk of not meeting its target completion date.

Additional Possibilities:

* Date and time tracking: Implement mechanisms to track actual time spent on tasks and projects for progress reporting and future estimation accuracy.
* Progress reporting: Develop functionalities to generate reports on project and task progress, including completion percentage, time remaining, and potential delays.
* Notifications and alerts: Set up automatic notifications to alert users about overdue tasks, approaching deadlines, and potential project risks.
* User roles and permissions: Define different user roles with varying access levels to manage projects, tasks, and data.
* Person class to manage the information about the individuals working on the project, including their skills, availability, and hours worked. This class could be referenced by the "Individuals Assigned" attribute in the Project class.

Person:
* Skills: A list of skills the person has, that can be used to better determine which projects and/or tasks they can be assigned to
* Availability: What time they normally work, to again, help better plan what projects and/or tasks they can be assigned to
* Hours Worked: The hours they worked on a specific project or task
* Name: The person's name
* Position: What position they hold within the company
* Worked Projects: A list of the projects they have previously worked on
* Worked Tasks: A list of the tasks they have previously worked on