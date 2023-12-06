---
title: Tools
date: 2018-12-18 18:00:00 Z
---

# Tools

Workato Tools help perform three main functions: Build recipes, connect apps and collaborate and manage recipes. Access the full list of tools using the navigation bar on the left side of the screen and select 'Tools'.

![Workato Tools](~@img/features/tools/tools-menu.png)
*Find all tools under the `Tools` menu*

## Building recipes

Tools for building recipes are often associated with connectors, triggers, and actions that users can select while building recipes. For example, setting up a lookup table in tools will allow the use of actions in the recipe which adds, removes, or updates the lookup table using the connector in a recipe.

![Using lookup table](~@img/features/tools/add-entry-to-lookup-table.png)
*Using the add entry action in a recipe creates new row in an existing lookup table*

These tools aid in making recipes more powerful with human approval capabilities as well as allow data to be reused across recipes in the same account.

The following are classified under this category:
<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
        <th width='25%'>Input field</th>
        <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td> <a href = "features/account-properties.html"> Properties </a></td>
      <td>
        Define account wide properties that you can use as variables in your recipes. <a href = "features/account-properties.html">Learn more</a>
      </td>
    </tr>
    <tr>
      <td> <a href = "features/lookup-tables.html"> Lookup table </a></td>
      <td>
        Define lookup tables that your recipes can easily lookup to get additional information. <a href = "features/lookup-tables.html">Learn more</a>
      </td>
    </tr>
    <tr>
      <td> <a href = "workflow.html"> People Task</a></td>
      <td>
        Add steps into your recipes that require a designated human to approve before it can continue. <a href = "workflow.html">Learn more</a>
      </td>
    </tr>
    <tr>
      <td> <a href = "features/message-template.html"> Message templates</a></td>
      <td>
        Create static message templates on HTML/text/JSON/XML that can be used in multiple recipes. <a href = "features/message-template.html">Learn more</a>
      </td>
    </tr>
    <tr>
      <td> <a href = "features/common-data-model.html">  Common data models </a></td>
      <td>
        Create schemas for objects such as Customers that can be used in multiple recipes. <a href = "features/common-data-model.html">Learn more</a>
      </td>
    </tr>
    <tr>
      <td><a href = "connectors/pubsub.html"> Pub/Sub</a></td>
      <td>
        Allow recipes to subscribe to events published by other recipes reducing dependencies and trickle down effects of change between recipes. <a href = "connectors/pubsub.html">Learn more</a>
      </td>
    </tr>
    <tr>
      <td><a href = "workbot/workbot.html"> Workbot for Slack</a></td>
      <td>
        Create a chatbot on slack that can interact with users to accomplish complex workflows. <a href = "workbot/workbot.html">Learn more</a>
      </td>
    </tr>
    <tr>
      <td> <a href = "workbot-for-teams/workbot.html"> Workbot for Microsoft Teams</a></td>
      <td>
        Create a chatbot on Microsoft Teams that can interact with users to accomplish complex workflows. <a href = "workbot-for-teams/workbot.html">Learn more</a>
      </td>
    </tr>        
  </tbody>
</table>


## Connect apps

Tools for connecting apps allow the user to add and manage their custom applications, on-prem applications and API endpoints.

The following are classified under this category:
<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
        <th width='25%'>Input field</th>
        <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href = "developing-connectors/sdk.html"> Connector SDK</a></td>
      <td>
        Build robust custom application connectors on Workato's Software Development Kit to connect to your any application we currently don't support. <a href = "developing-connectors/sdk.html">Learn more</a>
      </td>
    </tr>
    <tr>
      <td><a href = "on-prem.html"> On-prem agent</a></td>
      <td>
        Connect easily and securely to applications such as databases hidden behind firewalls. <a href = "on-prem.html">Learn more</a>
      </td>
    </tr>
    <tr>
      <td><a href = "api-management.html"> API Platform</a></td>
      <td>
        Turn any recipe or collection of recipes on Workato into an API endpoint that can be exposed to the public. <a href = "api-management.html">Learn more</a>
      </td>
    </tr>
  </tbody>
</table>

## Collaborate and manage recipes

The tools in this section allow the collaboration across teams, the management of team roles and sharing of recipes and dependencies between team accounts.

The following are classified under this category:

<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
        <th width='25%'>Input field</th>
        <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href = "recipe-development-lifecycle.html">Recipe lifecycle management</a></td>
      <td>
        Plan, develop, test, and deploy new workflows on Workato. <a href = "recipe-development-lifecycle.html">Learn more</a>
      </td>
    </tr>
    <tr>
      <td><a href = "user-accounts-and-teams/team-collaboration.html">Teams</a></td>
      <td>
         Collaborate with multiple users to build recipes in a share workspace. <a href = "user-accounts-and-teams/team-collaboration.html">Learn more</a>
      </td>
    </tr>
  </tbody>
</table>
