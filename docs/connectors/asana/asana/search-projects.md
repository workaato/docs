---
title: Workato connector - Asana - Search projects 
date: 2021-09-21 17:07:05 Z
---

# Asana Connector - Search projects 
This action will search projects in Asana.  If the workspace ID is specified, this action will only retrieve projects from the workspace.

## Input

| Field | Description |
|:--- |:--- |
| Workspace ID | The workspace ID. |
| Team ID | The team ID. It can be found in the URL of a team conversation. |
| Archived | Specify if you are searching for an archived project. |
{: .sdk-ref :}

## Output

| Field | Description |
|:--- |:--- |
| Projects |  This object contains projects belonging to the workspace (if a workspace ID is specified) or the organization. Each project contains the following fields.<ul><li>ID</li><li>Name</li></ul> |
{: .sdk-ref :}
