---
title: Create your first recipe
date: 2021-05-20 18:00:00 Z
---

# Create your first recipe
::: details Build your first recipe with this video guide
<Video src="https://www.youtube.com/embed/H4MMLklNpPU"/>
:::

A recipe is an automated workflow that connects your apps. Each recipe is comprised of a trigger and one or more actions. When you turn on your recipe, it waits for a triggering event to run the actions.

The following steps guide you through building a recipe that closes a case in Salesforce when an issue with the same name in Jira closes.

## Before you start
* To connect to your Jira account, you need the Host name, Email, and API token<br>
For information on how to generate the API token, see [create API token in Atlassian](/connectors/jira.md#how-to-connect-to-jira-on-workato)
* To connect to your Salesforce account, you need your username and password.



1. Navigate to **Assets** and click **Create Recipe**.
2. Enter `My first recipe` in the **Name** field.
3. Click **Start building**. ![Setup your recipe view](~@img/first-recipe/setup-recipe-view.png)

## Step 2: Connect to Jira
1. Search for the Jira app.
2. Select **Updated issue**.<br>The Connection page opens.
3. Enter a name for the connection in the **Connection name** field. <br>Since you can reuse connections between recipes, enter a descriptive name so you can identify the account. For example `Test Jira account`.
4. Enter the URL of your Jira account.
5. Select `Yes` to use an API token to authenticate.
6. Enter the email you use to login to Jira.
7. Enter the API token you retrieved from Atlassian.
4. Click **Connect**.<br>
You can now configure the trigger fields.

## Step 3: Set up the trigger
The recipe will run whenever an issue is closed. When you start the recipe, it will check for matching events from the previous seven days.
1. In the **When first started...** field, enter this formula: `7.days.ago`
2. Click to set a trigger condition.
3. In the **Recipe data** window, search for **Status > Name**.
4. Drag the **Name** datapill into the **Trigger data** field.
![Search for and drag the datapill](~@img/first-recipe/datapill.gif)
5. Set the condition to `contains`.
6. Set the value to `Closed`.
![Trigger fields](~@img/first-recipe/trigger-fields.png)

## Step 4: Connect to Salesforce
1. Click the + below **Actions** and click **Action in app**.
2. Search for the Salesforce app.
3. Select **Search records**.<br>The Connection page opens.
4. Enter a descriptive name for the connection in the **Connection name** field.
5. Click **Connect**.<br>
The Salesforce login page opens in a new window.
6. Enter your username and password and click **Log In**.<br>
You can now configure the action fields.

## Step 5: Set up the action
The recipe will search for cases in Salesforce with the same case name as the Jira issue.
1. In the **Search for** field, select **Case**.
2. Enter a limit of `150` records.
3. Drag the **Summary** datapill into the **Subject** field.
![Action fields](~@img/first-recipe/action-fields.png)

## Step 6: Set up the conditional statement
This step instructs the recipe to check if the Salesforce case is closed. If not, the recipe updates the status to closed.
1. Click the + below **Actions** and click **IF condition**.
2. Drag the **Status** datapill into **Data field**.
3. Select the **equals** condition.
4. Enter `Closed` in the **Value** field.
![Conditional step](~@img/first-recipe/if-condition.png)
5. Click to **Select an app..**.
6. Select the Salesforce app > **Update record**.<br>The action automatically selects the connection you established in Step 4.
7. Select **Case**.
8. Drag the **Case ID** datapill into the **Case ID** field.
9. Select the **Closed** status.
![Conditional step fields](~@img/first-recipe/if-condition-fields.png)

## Step 7: Save and start your recipe
1. Click **Save** then **Exit**.
2. Click **Start recipe**.
Your finished recipe should match this [recipe](https://app.workato.com/recipes/837151-closed-jira-issues-close-salesforce-cases?community=true)

## What is next
A few ideas for what you can do next:
- Explore the [Community library](https://app.workato.com/browse/recipes) to find ready-to-use recipes that other users built.
- Learn more about other types of triggers and actions in [recipe components](/recipes/building-recipes.md#learn-more-about-recipe-components)
