---
title: Custom OAuth profiles for Slack
date: 2018-04-9 10:23:00 Z
---

# What are custom OAuth profiles?
Custom OAuth profiles allow your Slack apps to leverage the Workato Slack connector under the hood. You can fully customize your Slack app's identity, i.e.:
- Branding (bot name, bot logos, background color)
- Permissions

# When would I need custom OAuth profiles for Slack
1. You want multiple apps that each perform workspace orchestration as part of their automations, for example, creating/archiving conversations. For example, an EscalationBot could create a private conversation, invite crisis management team members, and archive it once the issue is resolved. At the same time, BirthdayBot could perform the same actions – create a private conversation, invite the party planners, and archive it once the birthday is over – but for vastly different purposes.

2. You want control over your app's branding & appearance

3. You want control over your bot's permissions. The minimum permissions for optimal use are listed in the table below.
<table>
<thead>
  <tr>
    <th>Token type</th>
    <th>Scope</th>
    <th>Reason</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Bot</td>
    <td>None</td>
    <td>No bot scopes required.</td>
  </tr>
  <tr>
    <td rowspan="11">User</td>
    <td><code>channels:read</code></td>
    <td>Retrieves list of public conversations.</td>
  </tr>
  <tr>
    <td><code>channels:write</code></td>
    <td>Create/update public conversations.</td>
  </tr>
  <tr>
    <td><code>groups:read</code></td>
    <td>Retrieves list of private conversations.</td>
  </tr>
  <tr>
    <td><code>groups:write</code></td>
    <td>Create/update private conversations.</td>
  </tr>
  <tr>
    <td><code>im:read</code></td>
    <td>Retrieves list of direct message conversations.</td>
  </tr>
  <tr>
    <td><code>im:write</code></td>
    <td>Create/update direct message conversations.</td>
  </tr>
  <tr>
    <td><code>mpim:write</code></td>
    <td>Create/update multi-party group conversations.</td>
  </tr>
  <tr>
    <td><code>mpim:read</code></td>
    <td>Retrieves list of multi-party group conversations.</td>
  </tr>
  <tr>
    <td><code>chat:write</code></td>
    <td>Post messages as user.</td>
  </tr>
  <tr>
    <td><code>users:read</code></td>
    <td>Get user info.</td>
  </tr>
  <tr>
    <td><code>users:read.email</code></td>
    <td>Get user info by email.</td>
  </tr>
</tbody>
</table>

::: warning Migration to granular scopes
Slack released [granular permissions](https://api.slack.com/docs/token-types#granular_bot) on 22 January 2020. You may have to migrate any pre-existing custom Slack apps you have connected to Workato. See the [migration guide](/connectors/slack/slack-granular-permissions.md) for more details.
:::

# Setup requirements
To create a custom OAuth profile, you'll need access to [Custom OAuth profiles](https://app.workato.com/custom_oauth_keys) in Workato. 

If you are using another data center, log in to the custom profile for that data center:

- [EUDC Custom OAuth profile](https://app.eu.workato.com/custom_oauth_keys)
- [JPDC Custom OAuth profile](https://app.jp.workato.com/custom_oauth_keys)
- [SGDC Custom OAuth profile](https://app.sg.workato.com/custom_oauth_keys)
- [AUDC Custom OAuth profile](https://app.au.workato.com/custom_oauth_keys)

::: warning I Don't See Custom OAuth Profiles in My Workspace
Custom OAuth Profile is an added capability. Check with your Workato CSM to ensure that you have this capability enabled for your Workspace.
:::

# Creating a custom OAuth profile
## Step 1: Choose Slack

<Stepper>
<Step>

Before getting started, [sign in to your Slack workspace[(https://slack.com/signin#/signin) from your browser.

</Step>
<Step>

Navigate to **Tools > Custom OAuth profiles** in Workato. 

</Step>
<Step>

Click **New custom profile**.

</Step>
<Step>

On the **New custom profile** page:

- In Step 1, select **Slack**.
- In Step 2, provide a name for your new app, then click **Create new app.** This will open a new tab that brings you to https://api.slack.com/apps. Keep both the Workato tab and this new tab open - you'll need both to complete the remaining steps.

</Step>
</Stepper>

## Step 2: Create a new Slack app

<Stepper>
<Step>

In the new tab, select a workplace to develop the app in, then click **Next**.

</Step>
<Step>

Click **Create**.

</Step>
<Step>

In the "Welcome to your app's configurations" pop-up, click **Got It**.

</Step>
<Step>

Navigate to your app's **Basic Information** page. Scroll down to **App Credentials**, you will need the information here to complete the next step.

</Step>
</Stepper>

## Step 3: Configure Workato to talk to your Slack app

<Stepper>
<Step>

Head back to the Workato tab to complete Step 3.

</Step>
<Step>

In Step 3, fill in the following:

- **Client ID**: Paste the **Client ID** value from Slack into this field.
- **Client secret**: Paste the **Client secret** value from Slack into this field.
- **Verification token**:  Paste the **Verification Token** value from Slack into this field.

</Step>
<Step>

Click **Save** when you're finished.

</Step>
</Stepper>

## Step 4: Complete the connection in Workato

You're almost there! All that's left is to complete the connection in Workato.

<Stepper>
<Step>

In the open Workato tab, click **Done**. Go to any project folder to create a new Slack connection.

</Step>
<Step>

Provide a name for your Slack connection. In the **Custom OAuth profile** field, select the newly created OAuth profile. Click **Connect**.

</Step>
<Step>

In the permissions grant, click **Allow**.

</Step>
</Stepper>

---
