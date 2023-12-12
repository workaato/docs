---
title: Approval Bot accelerator - connect
date: 2022-19-03 00:00:00
topicType: task
---

# Connect the Approval bot accelerator to your applications {: #main :}

::: note REQUIRED APPLICATIONS
Where you plan to implement the Approval bot accelerator determines the applications you must connect. For example, if you plan to implement the Approval bot in Slack, you must connect Slack to your Workato workspace. Similarly, you must connect to MS Teams to implement the Approval bot in MS Teams.
::: 

## Connect to Slack {: #slack-connect :}

Add a custom bot to your Workato workspace and connect it to your Workato instance by following these steps:

<Stepper>
<Step>

Navigate to **Tools** and select **Workbot**.

![Create workbot](~@img/approval-workbot-create.png)

</Step>
<Step>

Configure the Workbot profile. Reference our [Workbot for Slack setup guide](/workbot/workbot-for-slack-setup.md) for instructions.

</Step>
<Step>

Navigate to **Approval Bot > Slack > Connections** and select **ABS | CON-001 | Workbot for Slack**.

</Step>
<Step>

Select **Approval Bot profile**.

</Step>
<Step>

Click **Connect**.

</Step>
</Stepper>

### Connect to MS Teams {: #teams-connect :}

<Stepper>
<Step>

In Workato, navigate to **Assets > Approval bot/MS Teams Workspace** folder.

</Step>
<Step>

Select **ABT | CON-001 | Teams Connection**.

</Step>
<Step>

Connect to Teams by authenticating your connection with Microsoft.

![Connect to teams](~@img/approval-connect-teams.png)

</Step>
</Stepper>

## Connect to Google Sheets {: #spreadsheet-connect :}

<Stepper>
<Step>

Connect to the spreadsheet.

![Connect to google sheets](~@img/approval-bot-connect-gsheets.png)_Connect to Google Sheets_

</Step>
<Step>

Google prompts you to allow Workato access. Click **Allow**.

</Step>
</Stepper>

::: note CUSTOMIZE CONNECTORS
The spreadsheet connector is a placeholder for the approval workflow of your choice. See [Customize the Approval bot for Slack](accelerator-approval-bot-customize-slack.md) or [Customize the Approval bot for Teams](accelerator-approval-bot-customize-teams.md) for instructions on replacing Google Sheets with an application of your choice. You can also contact customer success for support. 
::: 
