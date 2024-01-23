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

## Feature Details
### Track ideas, goals, projects, and tasks
#### General Thoughts

Ideally, I will want each of these to be custom built data structures. An idea would have a name, description, and any applicable notes. In addition to what an idea has, a goal would have assigned projects, start date, and due date. 
