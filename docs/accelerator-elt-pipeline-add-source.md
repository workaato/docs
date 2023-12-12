---
title: Add source and object
date: 2022-12-12 00:00:00
topicType: task
---

# Add sources and objects {: #add-source :}

::: note USER PERMISSIONS
This guide describes features that are only available to users with an **Admin** role. 
:::

To add a source and object:

<Stepper>

<Step>

In Slack or MS Teams, navigate to the **App homepage**.

</Step>
<Step>

Select **Add Source and Object**.

</Step>
<Step>

Configure the input fields in the **Add Source and Object** interface. 

<dl>
	<dt>Source system</dt>
		<dd>The source system to extract data from.</dd>
		<dd><dl class="horizontal-dl"><dt>Sample values:</dt>
			<dd><ul><li>Salesforce</li><li>Files</li><li>Microsoft SQL Server</li></ul></dd></dl></dd>
	<dt>Object</dt>
		<dd>This can be any object supported within the source system. In Salesforce, these are objects. In SQL Server and PostgreSQL these are table names.</dd>
		<dd><dl class="horizontal-dl"><dt>Sample values:</dt>
			<dd><ul><li>Leads</li><li>Accounts</li></ul></dd></dl></dd>
	<dt>Primary key</dt>
		<dd>If your data source is SQL Server or PostgreSQL, this is the primary key of your table. If you use any other source system, ELT Pipeline Bot ignores entries in this field.</dd>
		<dd><dl class="horizontal-dl"><dt>Sample value:</dt>
			<dd><code>primary_key</code></dd></dl></dd>
</dl>

</Step>
<Step>

Click **Submit**.

</Step>
</Stepper>