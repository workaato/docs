---
title: Workato connector - Asana - New or updated task 
date: 2021-09-21 17:07:05 Z
---

# Asana Connector - New or updated task 
This trigger checks for new or updated task in Asana. 

## Input

| Field | Description |
|:--- |:--- |
| Trigger poll interval | Select how frequently to check for new events. |
| When first started, this recipe should pick up events from | When left blank, trigger will start picking up tasks created or updated 1 hour ago. Once recipe has been run or tested, value cannot be changed. Learn more. |
| Workspace<br>**Required** | Use a Workspace or Project ID to filter tasks. Specify the Workspace to fetch assigned tasks in a workspace. Otherwise, you can specify the Project ID to fetch all tasks created under a specific project.  |
| Assignee ID | Specify which assignee you want to monitor. Tasks assigned to the logged in user will be fetched by default. Enter either email ID or ID of the people to whom the task is assigned.  |
{: .sdk-ref :}

## Output

| Field | Description |
|:--- |:--- |
| Task ID | The task ID. |
| Assignee | The people that are assigned to this task. |
| Assignee status | The status of the people assigned. |
| Completed | Whether the task is completed. |
| Completed at | The date and time when the task was completed. |
| Created at | The date and time when this record was created. |
| Due on | The date when the task is due. |
| Due at | The date and time when the task is due. |
| Followers | The people that follow this task. |
| Number of hearts | The number of hearts given to the task. |
| Hearts | The people who have added heart to the task. |
| Start on | The start date of this task. |
| Like this | Shows whether the authorized user has liked this task. |
| Number of likes | The number of likes added to the task. |
| Likes | The people that have liked this task. |
| Modified at | The date when the task was last modified. |
| Task name | The name of the task. |
| Description | The description of the task. |
| Projects | The projects that this task belongs to. |
| Parent Task | The parent task for this task. |
| Workspace | The workspace that this task belongs to. |
| Memberships | The membership details about this task. |
| Tags | The tags attached to this task. |
| Created by | The user that created this task. |
{: .sdk-ref :}

