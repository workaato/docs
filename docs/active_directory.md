---
title: Workato connectors - Active Directory
date: 2018-03-18 06:00:00 Z
---

# Active Directory
Active Directory is a directory service developed by Microsoft to manage access to resources in a network. The service runs on a Windows Server.

## How to connect to Active Directory on Workato
The Active Directory connector authenticates with LDAP protocol, which is only available via the on-premise agent.

::: tip When setting up connection directly in workato using cloud profile
You don't have to edit on-prem config file, set up all properties directly in workato as shown below.
:::

![Configured Active Directory connection](~@img/active_directory/connection.png)

<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
        <th width='25%'>Field</th>
        <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Connection name</td>
      <td>Give this Active Directory connection a unique name that identifies which Active Directory instance it is connected to.</td>
    </tr>
    <tr>
      <td>On-prem group</td>
      <td>Choose an on-premise group if your database is running in a network that does not allow direct connection. Before attempting to connect, make sure you have an active on-premise agent. Refer to the <a href="/on-prem.html">On-premise agent</a> guide for more information.</td>
    </tr>
    <tr>
      <td>On-prem LDAP connection profile</td>
      <td>Profile name defined in your <code>config.yml</code> file in the on-premise agent. This option is visible when you select on-prem group that supports <a href="/on-prem/groups/create-group.html#manually-in-each-agent-connection-profiles">connection profile</a>.</td>
    </tr>
    <tr>
      <td>On-prem LDAP connection profile</td>
      <td>Profile name defined in your <code>config.yml</code> file in the on-premise agent.</td>
    </tr>
    <tr>
      <td>URL</td>
      <td>The URL should be in the format ldap://myserver.example.com:389 or ldaps://myserver.example.com:636 for SSL</td>
    </tr>
    <tr>
      <td>Username</td>
      <td>The username (principal) to use when authenticating with the LDAP server. This will usually be the distinguished name of an admin user</td>
    </tr>
    <tr>
      <td>Password</td>
      <td>The password (credentials) to use when authenticating with the LDAP server</td>
    </tr>
     <tr>
      <td>Base</td>
      <td>The base DN for all requests. When this attribute has been configured, all Distinguished names supplied to and received from LDAP operations will be relative to this LDAP path.</td>
    </tr>
    <tr>
      <td>Certificate</td>
      <td>Path the PEM encoded certificate or a trusted CA</td>
    </tr>
    <tr>
      <td>SSL certificate</td>
      <td>Full content of a PEM encoded client certificate</td>
    </tr>
    <tr>
      <td>SSL certificate key</td>
      <td>Private key for mutual SSL setup. Required if SSL certificate is provided.</td>
    </tr>
     <tr>
      <td>Trust all</td>
      <td>Select true to enable self-signed certificates.</td>
    </tr>
  </tbody>
</table>

## Working with the Active Directory connector

### Object types
The Active Directory connector works with all types of objects.

### Sample entry DN
Use this field to define the object that you want to work with. The value in this input field should be an actual entry in your Active Directory instance. This entry will be used to determine the input and/or output fields of the action/trigger.

DN of a sample user entry will look like this:

```
CN=Workato Integrations,CN=Users,DC=workato,DC=local
```
