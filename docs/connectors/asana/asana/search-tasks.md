---
title: Workato connector - Asana - Search tasks 
date: 2021-09-21 17:07:05 Z
---

# Asana Connector - Search tasks 
This action will search tasks in a specified workspace in Asana.

## Input

| Field | Description |
|:--- |:--- |
| Workspace ID<br>**Required** | The workspace ID. |
| Assignee ID | The assignee ID. Leave empty to get tasks assigned to the authorized user. |
{: .sdk-ref :}

## Output

| Field | Description |
|:--- |:--- |
| Tasks | This object contains all tasks that belongs to the assignee. Each task contains the following fields.<ul><li>ID</li><li>Name</li><li>Created by</li></ul> |
{: .sdk-ref :}

