---
title: Workato connector - Asana - Update task 
date: 2021-09-21 17:07:05 Z
---

# Asana Connector - Update task 
This action will update task in Asana.

## Input

| Field | Description |
|:--- |:--- |
| Task ID<br>**Required** | The task ID. You can find the task ID at the end of URL of the task page. |
| Projects | The projects that this task belongs to. |
| Task name | The name of the task. |
| Description | The description of the task. |
| Assignee | The people that are assigned to this task. |
| Assignee status | The status of the people assigned. |
| Completed | Whether the task is completed. |
| Due on | The date when the task is due. |
| Due at | The date and time when the task is due. |
| Heart this | Whether to add a heart to this task. |
| Start on | Schedule a start date. If this value is provided, either "Due on" or "Due at" field should be specified |
| Like this | Whether to add a like to this task. |
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
| Heart this | Whether the authorized user has hearted this task. |
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


