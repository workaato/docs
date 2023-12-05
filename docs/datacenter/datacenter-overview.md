---
title: Data center overview
date: 2021-03-22 06:00:00 Z
tags:
    - EU Data Center
    - Europe
    - EEA
    - JP Data Center
    - Japan
    - SG Data Center
    - Singapore
    - AU Data Center
    - Australia
---

# Supported cloud regions
As a Workato customer, you can choose the region where to store and process your organization’s automation data. This includes recipes, connections, shared assets like lookup tables, and the job history. This data remains isolated within that specific region; it cannot be transferred to other regions.

This approach allows you to localize your data and processing in specific locations if desired or required for legal and regulatory compliance.

::: tip SECURITY MEASURES ARE THE SAME ACROSS DATA CENTERS
Visit https://www.workato.com/legal/security to learn more about how Workato addresses security.
:::

![Workato data center locations](~@img/international-datacenters.png) 
_Workato data center locations_

## Data center locations

Workato customers can host their data in the following regions:

<dl>
<dt>US Data Center</dt><dd>The US Data Center is hosted on Amazon Web Services (AWS) in the US East region. It is available for Workato customers in the North America region.</dd>
<dt>EU Data Center</dt><dd>The European Union (EU) data center is available for customers in the European Economic Area (EEA) who prefer to store and process their data locally. The new data center is hosted in the AWS EU Central region.</dd>
<dt>JP Data Center</dt><dd>The JP Data Center is available for customers who require their data within Japan.</dd>
<dt>SG Data Center</dt><dd>The SG Data Center is available for customers who require their data within Singapore.</dd>
<dt>AU Data Center</dt><dd>The AU Data Center is available for customers who require their data within Australia.</dd>
</dl>

<p></p> <!-- add padding -->

::: tip WORKATO ACROSS REGIONS
Each Workato account is hosted in a single regional data center. If you want to use Workato across multiple regions, you must sign up for and maintain a Workato account in each of the desired regional data centers.

Learn more about [sharing assets across regions](#sharing-assets).
:::

## Sharing of data between regions
Workato does not share or transfer customer data across regions. Each data center in the region independently hosts customer accounts. The customer data that is in an account in one region cannot be shared with an account in a different region.

Workato collects certain kinds of data to provide services. Such data may be transferred to and stored in the US. This data includes:
- in-app chat
- support tickets and other interactions with the Workato support
- interactions with the Workato blog
- interactions with Workato educational offerings like the Automation Institute

To learn more about the information we collect, see the [Privacy policy](https://www.workato.com/legal/privacy-policy).

## Customer support
Workato maintains a globally-distributed support team to offer product support to our customers in all timezones.

## Can I share assets across data centers? {: #sharing-assets :}
The following forms of cross data center collaboration are not enabled:

- **Cross-region user collaboration.**
In this scenario, a user of a Workato account in the US Data Center wants to join as a collaborator in a Workato account in the EU Data Center. The collaboration may result in customer data transfer between the two regions. To avoid such data transfers, cross-region collaboration is not supported.

- **Cross-region recipe sharing using shared token.**
Users can share their recipes by sending other users the recipe URL with the shared token. Customer integration data is stored in the data center where their Workato workspace is hosted. Thus the recipe URL is specific to the data center where the recipe is stored, and can only be accessed by users who have an account in the same region.

- **Cross-region custom connector sharing via the shared token.**
Similar to recipe-sharing, users can send other users their custom connectors via the connector URL with the shared token. Custom connectors built using the Connector SDK are stored in the data center where the Workato workspace is hosted. The connector URL is specific to the data center where the connector is stored, and can only be accessed by users who have an account in the same region.
