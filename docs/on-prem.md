---
title: On-prem Connectivity
date: 2023-01-25 12:00:00
tags:
    - on prem agent
    - on premise agent
    - on premise connectivity
topicType: general
---

# On-prem Connectivity
<br>
<Video src="https://www.youtube.com/embed/iAb2xXk9R8I" />

Enterprises deploy applications and databases within a restricted network to exercise greater control over security and privacy. Firewalls monitor and regulate the flow of data between these private environments and the public internet. Therefore, applications and data hosted on these private IT environments are typically not accessible to cloud services like Workato.

Using Workato's on-premise agent, we can create a secure connection from within your private IT environment to connect to Workato cloud. This allows you to fully integrate your hybrid cloud or multicloud architecture while maintaining control over security.

> On-prem access is enabled only for certain users. Reach out to your Customer Success Manager to learn more.

## Overview
The following is a conceptual model of Workato's on-prem agent and how it interacts with databases and applications behind the firewall.

![On-prem model](~@img/on-prem/on_prem_conceptual_model.png)
*Conceptual model for on-prem agent and connector*

On-prem agents can also be installed into logical groups, called [On-prem groups](/on-prem/groups.md), to achieve **High Availability** and **Load Balancing** capabilities.

![On-prem group model](~@img/on-prem/on_prem_group_conceptual_model.png)
*Conceptual model for on-prem agents in a group*

## How it works
Workato on-prem connectivity has two core components:
- Tunneling
- Database, file system, and application access.

The on-prem agent runs within the user's server, typically behind a firewall, and establishes a TLS WebSocket tunnel to connect out to Workato.

Because the on-prem agent is within the same network as systems behind the firewall, it can safely access them and act as the agent to communicate securely out to Workato.

## Supported operating systems
The on-prem agent runs on the following systems:

- Linux (64-bit)
- Windows 7, 10, 11 (64-bit)
- Mac OS X
- Windows Server 2008 and newer (before OPA [v2.8.0](/on-prem/agents/versions.md#v2-8))
- Windows Server 2012 R2 and newer (OPA [v2.8.0](/on-prem/agents/versions.md#v2-8) onwards)

Minimum hardware requirements are:

- 8 GB of RAM
- 250 MB of disk space
- 800 Mhz 64-bit CPU (Intel/AMD).

Learn how to setup an OPA for each operating system in our [on-prem setup guide](/on-prem/agents/setup.md).

## Can the OPA be used in multicloud and public clouds?
Yes, Workato's OPA can be use in any IT environment. You can run the OPA on a public cloud like [Amazon Web Service](https://aws.amazon.com/), [Azure cloud](https://azure.microsoft.com/en-us/), or [Google Cloud Platform](https://cloud.google.com/). You can also run the OPA on a private machine.

The OPA runs on any virtual or physical machine as long as there is a compatible operating system. Learn more about [supported operating systems](#supported-operating-systems).

## On-prem permissions
You can configure access to on-premise features using Workato [role-based access control](/privileges.md#on-premise).

## In this section
* [On-prem group](/on-prem/groups.md)
  * [Create a group](/on-prem/groups/create-group.md)
  * [Add agent to a group](/on-prem/groups/add-agent.md)
  * [Status of a group](/on-prem/groups/group-status.md)
  * [Common configuration](/on-prem/groups/common-config.md)
* [On-prem agent](/on-prem/agents.md)
  * [Setup agent](/on-prem/agents/setup.md)
  * [Run agent](/on-prem/agents/run.md)
  * [Upgrade agent](/on-prem/agents/upgrade.md)
  * [Profiles](/on-prem/agents/connection/profile.md)
  * [On-prem connections](/on-prem/agents/connection.md)
  * [Password encryption](/on-prem/agents/password-encryption.md)
  * [Proxy server](/on-prem/agents/proxy.md)
  * [Logging](/on-prem/agents/logging.md)
  * [Extensions](/on-prem/agents/extension.md)
