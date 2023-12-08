---
title: Recipe Components - App Connections
date: 2021-10-21 18:00:00 Z
---

# App connections

::: tip SUMMARY
- Workato connects to apps to build recipes, with each connection reusable across multiple recipes.
- Connections require the "Create Connections" privilege and use the app's authentication API with various methods like OAuth or Basic authentication.
- Workato's data access is tied to the user's permissions, and connections can be made within the recipe editor or through the connection wizard.
- Multiple app instances require distinct connections.
:::

::: details Watch a quick video guide

<Video src="https://www.youtube.com/embed/m3lajUatO7w" />

:::

When you start building a recipe, the first step is establishing a connection between Workato and an app.

Each connection is associated with one instance of the app, such as a user account, and can be re-used across recipes.

In this guide, we'll cover:

- [Connection basics](#connection-basics)
- [Creating connections](#creating-connections)
- [Using connections in recipes](#using-connections-in-recipes)
- [How to handle connection errors](#connection-errors)

---

## Connection basics 

- [Who can create connections?](#who-can-create-connections)
- [How does Workato access my connections?](#how-does-workato-access-my-connections)
- [What data can Workato access in my connections?](#what-data-can-workato-access-in-my-connections)
- [What best practices should I follow?](#what-best-practices-should-i-follow)

### Who can create connections?

To create connections, you need the [**Create Connections** privilege](/privileges.md#connection).

Refer to the [Creating connections](#creating-connections) section for instructions.

### How does Workato access my connections?

Workato typically uses the app's authorization/authentication API to establish the connection, using one of the following methods:

- OAuth 2.0
- OAuth 1.0 (and variations)
- Basic authentication (username and password)
- API key or secret

As part of this step, you provide Workato with the permission to access data from the app. The permissions granted to Workato usually correspond with those of [the user authorizing the app](#what-data-can-workato-access-in-my-connections).

Refer to the [connector documentation](/connectors.md) for your app for more info on how to connect to Workato.

### What data can Workato access in my connections?

Workato can only access the same data the user authorizing the connection has access to.

For example: If you only have access to view accounts in Salesforce and you create a Salesforce connection in Workato, Workato will only be able to view accounts.

### What best practices should I follow?

When creating connections, we recommend:

- [Creating a dedicated user for Workato](#creating-a-dedicated-user-for-workato)
- [Using sandbox credentials for development](#using-sandbox-credentials-for-development)

#### Creating a dedicated user for Workato

Creating a dedicated app user for Workato ensures that recipes aren't dependent on the account of a human user. If someone leaves the company, recipes will continue to run.

Additionally, creating a dedicated Workato user allows you to tailor the permissions Workato has in the app, thereby reducing security risk.

Apps have different granularity when it comes to defining user roles and permissions. Refer to the [connector documentation](/connectors.md) for your app for more info.

#### Using sandbox credentials for development

When developing and testing recipes, we recommend using sandbox (or non-production) credentials for your connections. Using test data during development ensures that live data isn't accidentally altered.

For additional info, refer to the [Using connections in recipes](#using-connections-in-recipes) section.

---

## Creating connections

There are two ways to connect apps in Workato:

- [In the recipe editor](#in-the-recipe-editor)
- [In the connection wizard](#in-the-connection-wizard)

### In the recipe editor

To add a connection while in the recipe editor:

<Stepper>
<Step>

In the recipe editor, click an app from the side menu.

</Step>
<Step>

Click the trigger or action you want to use.

</Step>
<Step>

Follow the prompts and [setup guide](/connectors.md) for the app.

</Step>
</Stepper>

![Connection via new recipe](@img/recipes/app-connections/via-new-recipe.gif)

### In the connection wizard

You can access the connection wizard from a few places in Workato:

- **Resources > Connections > Create connection**
- **Resources > Recipes > Create connection**
- **Any project > Create connection**

![Connection via new connection](@img/recipes/app-connections/via-new-connection.gif)

---

## Using connections in recipes

::: warning IMPORTANT!
Before triggers and actions can be configured in recipes, valid connections to apps must be established.
:::

- [Multiple app instances, one recipe](#multiple-app-instances-one-recipe)
- [Runtime user connections](#runtime-user-connections)

### Multiple app instances, one recipe

Typically, you'll have one or two instances of an app - one for production and perhaps another for testing. In a scenario like this, you'd likely need one connection to use across multiple recipes.

When you have multiple instances of an app, multiple connections should be created in Workato. Each connection should authenticate to each instance of the app.

Most connectors only allow one connection per app, per recipe. Should you need to work with two separate instances of an app, you can use [Secondary connectors](/features/secondary-connectors.md).

::: note SECONDARY CONNECTORS

Workato *does not* support secondary connectors for all Workato connectors.

If the app(s) you plan to use do not have secondary connectors, then you are limited to one connection per app, per recipe.

If you try to connect to multiple instances of an app that does not support secondary connectors within the same recipe, Workato prevents you from doing so. When you create the second connection, it will automatically override your first connection and replace it with the second connection.

For example, let's say you have a recipe trigger called **New email in Gmail** that uses the **My Gmail account** connection. If a subsequent step in the recipe also involves a Gmail action, it must use the same connection. If you attempt to use a different connection, such as **My second Gmail account**, Workato will update the **New email in Gmail** trigger's connection to **My second Gmail account**.

:::

### Runtime user connections

:::tip AVAILABLE IN CALLABLE & WORKBOT RECIPES
The **Runtime user connections** feature is only available in Callable or Workbot recipes.
:::

By default, recipes perform actions based on the credentials used to authorize the connection. However, by using the **Runtime user connection** feature, you can swap out connections when a recipe runs. 

For example: Let's say you have a recipe that creates opportunities in Salesforce. The Salesforce connection currently uses a Sales Manager's credentials. Even though other sales reps are creating opportunities, all opportunities will show as created by the Sales Manager.

Learn more in the [Runtime user connections docs](/features/runtime-user-connections.md).

---

## Connection errors

On occasion, app connections can become invalid. These are the most common reasons:

- **Modified credentials.** If credentials were changed in the app and not in Workato, the connection may become invalid.
- **Insufficient permissions.** In this case, the user authorizing the connection doesn't have the permissions to access required data or perform certain actions.

If you encounter an invalid connection error, we recommend:

- **Verifying the authorizing user's permissions.** Verify that the user who is authorizing the connection has sufficient permissions.
- **Verifying that the connection's credentials are correct.** Double-check that the password, API key, etc. is entered correctly.
- **Re-authorizing the connection.** If you've verified the user's permissions and credentials, try re-connecting the connection.

![Design-time errors for app connection errors](~@img/recipes/troubleshooting/connection-error.png)
*Design-time errors for app connection errors*

---
