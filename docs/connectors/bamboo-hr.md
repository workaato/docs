---
title: Workato connectors - Bamboo HR
date: 2020-07-01 18:00:00 Z
---

# Bamboo HR

[Bamboo HR](https://www.bamboohr.com/) is a HR software solution for collecting, maintaining, and analyzing your people data.

## API version

The Bamboo HR connector uses [Bamboo REST API v1](https://documentation.bamboohr.com/).

## How to connect to Bamboo HR on Workato

![Bamboo HR connection setup](~@img/connectors/bamboo-hr/connect-to-bamboo-hr.png)
_Bamboo HR connection setup_

| Input field     | Description                                                                                 |
| --------------- | ------------------------------------------------------------------------------------------- |
| Connection name | Give this connection a unique name that identifies which instance it is connected to.       |
| API token       | The API token. Learn how to [create this API token](#how-to-create-an-api-key-on-bamboo-hr) |
| Sub-domain      | The base URL of your Bamboo HR instance.                                                    |

## How to create an API key on Bamboo HR

| Steps | Description                                                                                                                                                                                                                                                              |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1.    | Navigate to **Profile** > **API keys**<br>![Navigate to Bamboo HR API keys](~@img/connectors/bamboo-hr/find-api-keys.png)<br>_Navigate to Bamboo HR API keys_                                                                                                            |
| 2.    | Create a new API key by selecting **Add New Key**<br>![Add new API key](~@img/connectors/bamboo-hr/add-new-api-key.png)<br>_Add new API key_                                                                                                                             |
| 3.    | Provide a descriptive name for this new API key. For example, `workato_user`.<br>![Add new API key](~@img/connectors/bamboo-hr/add-api-key-name.png)<br>_Add new API key_                                                                                                |
| 4.    | An API key will be generated. Save this key in a secure location.<br><br>Note that this API key is only visible here. You will no longer be able to retrieve this key after this step.<br>![Save API key](~@img/connectors/bamboo-hr/save-api-key.png)<br>_Save API key_ |

For more information, see the [Bamboo HR documentation](https://documentation.bamboohr.com/docs#authentication).

## Triggers and actions

You can browse the other chapters:

### Bamboo HR triggers

- [New employee trigger](/connectors/bamboo-hr/new-employee-trigger.md)
- [New employee trigger (real-time)](/connectors/bamboo-hr/new-employee-realtime-trigger.md)
- [Updated employee trigger](/connectors/bamboo-hr/updated-employee-trigger.md)
- [Updated employee trigger (real-time)](/connectors/bamboo-hr/updated-employee-realtime-trigger.md)
- [Schedule custom employee report trigger](/connectors/bamboo-hr/schedule-custom-report-trigger.md)

### Bamboo HR actions

- [Create employee action](/connectors/bamboo-hr/create-employee-action.md)
- [Create/update time off request action](/connectors/bamboo-hr/create-update-time-off-request-action.md)
- [Update employee action](/connectors/bamboo-hr/update-employee-action.md)
- [Update time off request status action](/connectors/bamboo-hr/update-time-off-request-status-action.md)
- [Get employee details by ID action](/connectors/bamboo-hr/get-employee-details-action.md)
- [List employees in directory action](/connectors/bamboo-hr/list-employees-in-directory-action.md)
- [List time off requests action](/connectors/bamboo-hr/list-time-off-requests-action.md)
- [Get table records of employee action](/connectors/bamboo-hr/get-table-records-of-employee-action.md)
- [Create custom employee report action](/connectors/bamboo-hr/create-custom-report-action.md)
- [Get company employee report by ID action](/connectors/bamboo-hr/get-company-report-by-id-action.md)
