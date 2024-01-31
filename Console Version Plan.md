## General Concepts

Build a console based task manager. For now, don't worry about building it as a graphical task manger. I can add that later. I have a lot to learn about building the front end side of things anyway. I want to start with an idea, this will have a name for the idea and a description. From there, once a project is attached to the idea, it will become a goal. Both projects and goals can have individual target dates set for them. Projects can then have tasks added to them. Ideas, goals, projects, and tasks can have notes added to them. 

I want the ability to display a goal and all of its attached projects, along with all of the related tasks. I also want the ability to see just the goals, projects, or tasks. I want to build an idea list, this will be a list of ideas that can eventually be turned into goals. All that needs to happen to turn an idea into a goal is to add a project to it. Goals, projects, and tasks will all have due dates, current status tracking, and the ability to add notes. Obviously, I will need the ability to create, edit, and delete goals, projects, and tasks. I want the task manager to automatically show a list of the next few tasks, projects, and goals that are due. It will also show any overdue goals, projects, or tasks that are overdue. 

I also want to add the ability to track requirements going both directions on both tasks and projects. For example, I want to be able to track if a certain project needs to be completed before another project can start, and have that be able to be tracked going both directions. Accordingly, I want to also put warnings built into projects and tasks letting you know if you are putting the project behind by not getting done on time. Taking it one step farther, I want to be able to attach to each project and task, the requirements that must be completed before hand, the estimated time to completion, and the project start date, and then have the tool give you a suggestion for how to organize the project to be able to complete it in as short of time as possible. I also want to be able to tell the project how many expected man hours it will take to complete each project/task, and how many are available for the duration of the project/task so that it can use that to better suggest the fastest route to completion. Accordingly, I think I want to be able to tell the program how many people I have, how many hours they work and what skills/projects/tasks they can work. I also want to track the needed resources for each project/task.

I want to be able to track the actual amount of time worked (via estimating the number of hours worked in a day not through actual reporting) on a project/task. I want to be able to get a projection based on time taken so far, for how long it will take to complete the project and compare that to the target completion date. And I want a progress report feature that could be used to report on progress for the day. 

I also want to add in analytics technology to be able to try to predict how long it will take a person to perform a project/task based on prior projects/tasks with similar skills. Ideally, I want this information in some form to be available to supervisors and employees. The goal for both will be to help them learn where there are weaknesses so they can better plan for improvement. My first thought for how to complete this is to simply track how long a job takes and then create a data structure of some sorts for each skill to then average out the length of time it takes for jobs involving that skill. I had the specific thought to track both the raw data, and the difference between the actual time and estimated time. As I think about this, I would also want to do the same thing with the skill of estimating the time to complete a job, and try to use that to generate better estimates of how long the job will take. 

## Features List

* Track ideas, goals, projects, and tasks (collectively referred to objects)
* Create, edit, and delete ideas, goals, projects, and tasks
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
* Predictive Analytics that use prior data to better forecast both the actual time it will take to complete the job, and to generate more accurate forecasts
* Easy access for all parties to use forecasting data to figure out where they need to improve

## Feature Details
### Track ideas, goals, projects, and tasks
#### General Thoughts

Ideally, I will want ideas, goals, projects, and tasks to all be custom built data structures. 
#### Ideas:

* Name: Short and descriptive name for the idea.
* Description: Detailed description of the idea, including its purpose and potential benefits.
* Notes: Any additional information or thoughts about the idea.
* Priority: (Optional) A way to prioritize ideas for future development.
* Date created: (Optional) Timestamp of when the idea was created.

#### Goals:

* Inherit all data from the Idea class.
* Target date: Desired completion date for the goal.
* Projects: List of associated projects that contribute to achieving the goal.
* Status: Current progress status of the goal (e.g., in progress, on hold, achieved).
* Progress: The percentage of the goal that has been achieved.
* Start Date: The date when work towards this goal begins.
* Due Date: The target date for achieving this goal.

#### Projects:

* Inherit all data from the Goal class.
* Tasks: List of tasks required to complete the project.
* Resources: List of resources needed for the project (e.g., equipment, software, data).
* Skills: List of skills required for project completion.
* Team: List of individuals assigned to the project.
* Estimated time: Total estimated time required to complete the project.
* Start date: Planned start date for the project.
* Available People: A list of people with the skills needed to work on this project/task.
* Assigned People: A list of the current people assigned to this project/task
* Dependencies: List of other projects that need to be completed before this project can start (and vice versa).
* Risk assessment: (Optional) Potential risks associated with the project and mitigation strategies.
* Warnings: Alerts if the project is at risk of not meeting its target completion date.

#### Tasks:

* Inherit all data from the Project class.
* Supplies: List of specific supplies needed to complete the task.
* Estimated time: Estimated time required to complete the task.
* Actual Time Spent: The actual time spent on the task so far.
* Priority: Priority level within the project (e.g., high, medium, low).
* Status: Current progress status of the task (e.g., open, in progress, completed).
* Assigned to: Individual assigned to the task (optional).
* Dependencies: List of other tasks that need to be completed before this task can start (and vice versa).
* Warnings: Alerts if the project is at risk of not meeting its target completion date.

#### Additional Possibilities:

* Date and time tracking: Implement mechanisms to track actual time spent on tasks and projects for progress reporting and future estimation accuracy.
* Progress reporting: Develop functionalities to generate reports on project and task progress, including completion percentage, time remaining, and potential delays.
* Notifications and alerts: Set up automatic notifications to alert users about overdue tasks, approaching deadlines, and potential project risks.
* User roles and permissions: Define different user roles with varying access levels to manage projects, tasks, and data.
* Person class to manage the information about the individuals working on the project, including their skills, availability, and hours worked. This class could be referenced by the "Individuals Assigned" attribute in the Project class.

#### Person:
* Skills: A list of skills the person has, that can be used to better determine which projects and/or tasks they can be assigned to
* Availability: What time they normally work, to again, help better plan what projects and/or tasks they can be assigned to
* Hours Worked: The hours they worked on a specific project or task
* Name: The person's name
* Position: What position they hold within the company
* Worked Projects: A list of the projects they have previously worked on
* Worked Tasks: A list of the tasks they have previously worked on
* Email address: Their email address
* Other Contact info: A list of other contact info the person wishes to provide

### Create, edit, and delete ideas, goals, projects, and tasks

Not much to explain in this. The details of how to create, edit, and delete items would need to be figured out after more has been planned about the details to the structure of the app. 

### Use current date to show objects by due date and flag any overdue objects

Will use the current date of the system, compare that to the projects/tasks in the app, and then automatically display a warning message about overdue projects/tasks. 
Will also show how long until the project/task is due. 

### Automatically show any overdue objects upon loading of the program

Same as above except it displays to the main screen

### Automatically show a list of any objects that are due soon

Same as above except it displays to the main screen

### Automatically convert an idea into a goal when a project is attached to it

Behind the scenes this will automatically remove the goal from the data structure storing all current goals, and add the details of that goal to a newly created project. This will require many data fields to be optional to work properly. 

### Display all objects attached to a goal 

This will display a goal, any anything that might be attached to it, or an item attached to it. 

### Display all tasks attached to a project

This will display all tasks attached to the selected project

### Display all tasks

This will display all current tasks regardless of the project they are attached to

### Display all projects

This will display all current projects

### Display all goals

This will display all current goals. 

### Attach due dates to any object other than an idea

All dates should be easily searchable. Would also want the process of pulling the data out in O1 time. For Python, this could be accomplished by a dictionary with the due date stored using the date or due_date keyword. I would imagine similar concepts could be accomplished in C#, JavaScript, and Kotlin. 

### Track project/task requirements going both directions

I could attach a variable to each project/task that would track what projects/tasks that could act like a linked list of sorts. One variable could be used to look for the project with the appropriate name. It would be nice if I could somehow guarantee that it will point to the right place, using names will only work if I can guarantee that the names will be unique, and while I could add that qualification, I think there should be a better way. I will have to put some thought into how to do that. One possibility is that I just assign each project/task a unique identifier. One simple way to do that is to use the date the project/task was created as the start to a number and then add on an extra number based on the sequence the project/task was created in. For example, if 3 tasks had been created on 27 January 2024, the task numbers could be 12720240, 12720241, and 12720242, thus rendering a constantly unique number to use for each project or task. 

### Track the number of people working on the project, the number of hours they work, and which tasks/projects they can work on. 

While a report will need to be built to make this more user friendly, the functionality can be built into the different data structures to track all of these features. 

### Track the skills required for each project, and the skills each person has

Same as above, the functionality for this can be built into the different data structures to track required skills. 

### Use project/task requirements along with required skills and estimated hours to complete and then the skills and available hours for each project/task to create an suggested minimum completion time. 

The requirements I want to have are as follows:
* The ability to set how many hours are available per day put towards projects/tasks. 
    > The reason this is important is because if there are 4 projects/tasks that each require 8 hours of work and that have no prerequisites but only have two employees to put towards the projects then the system might try to suggest that they work on all 4 at the same time. So, this means that I would need to take into account the available hours. 
* A required field for project/task creation will be to tell the system what project/s or task/s would need to be completed before this project/task. 
* A project/task that has no prerequisite project/task, would be added to the list of head projects/tasks. 
* Each project/task, will have two time estimates built into it. One that shows just how long to complete it, and one that shows how long to complete it and everything that follows it. This will be updated upon creation of a project/task for any project/task that needs to be completed before it is started. 
    > Possible implementation, create a list of projects/tasks that need to be completed first, and add it to the data that each project uses. From there, when we assign a project as a prerequisite of another, the list it has could be copied to the project/task being created and then we would just add the newly assigned prerequisite project/task to the list for the newly created project/task. Thus for updating time to complete, we would only need to iterate through the new project's prerequisite list. 

Steps to build suggested minimum completion time for projects/tasks. 
* Check available hours per day for working on projects/tasks
* With projects/tasks prerequisites already set, select project/task head that has the longest time to complete when factoring in the projects/tasks that have that as a head. 
    * If multiple projects have the same prerequisite, then check if there are enough hours to work all projects. 
        * If not, select the project/task sequence that would take the longest to complete.
        * Start any branches of the longest project chain, the moment enough time becomes available by order of longest to complete. 
* Fill in any projects/tasks that do not have any other tasks that use them as a prerequisite as enough hours become available. 
    * Fill any open slots with the project/task that would use the most of that time. 


### In project/task warnings letting them know if they are risking affecting the project completion target

### Track needed resources for each project/task

### Estimate the target completion date based on current progress. 

### Get and track progress reports for projects and tasks. 

### Track information about the people assigned to the project/task

### Predictive Analytics that use prior data to better forecast both the actual time it will take to complete the job, and to generate more accurate forecasts

### Easy access for all parties to use forecasting data to figure out where they need to improve
