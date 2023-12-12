---
title: Workato connector - Asana - Search tags 
date: 2021-09-21 17:07:05 Z
---

# Asana Connector - Search tags 
This action will search tags in Asana. If the workspace ID is specified, this action will only retrieve tags from the workspace.

## Input

| Field | Description |
|:--- |:--- |
| Workspace ID | The workspace ID. |
| Team ID | The team ID. It can be found in the URL of a team conversation. |
{: .sdk-ref :}

## Output

| Field | Description |
|:--- |:--- |
| Tags | This object contains tags belonging to the workspace (if a workspace ID is specified) or the organization. Each tag contains the following fields.<ul><li>ID</li><li>Name</li></ul> |
{: .sdk-ref :}

