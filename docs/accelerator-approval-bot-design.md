---
title: Approvals bot accelerator - Design
date: 2022-12-29, 15:00:00 Z
summary: "Automate the process of processing app approval requests."
topicType: concept
---

# Solution design overview

Workato's **Approval bot accelerator** consists of multiple recipes and lookup tables. Implement the Approval bot manifest with your connection to Slack or MS Teams and the source applications of your choice. This framework enables the Approval bot to perform the following actions:

- [Synchronize approvals from different applications in a central location](#approvals-synchronize)
- [Send reminders for pending approvals](#reminders-send)
- [Provide a dashboard overview of all requests for approvals](#dashboard-overview)

---

### Synchronize approvals from specified applications {: #approvals-synchronize :}

Workato routes approvals from multiple source applications you specify to one central Approvals bot within Slack or MS Teams. After an approver processes a request, Workato updates the record and sends a message to the requester in Slack. Then, the approvers you designate can approve or reject requests with comments. Workato delivers these comments to the requester and source application. 

Approval requests contain the application requested, the requester, a request description, and the date of the request.  

---

### Send reminders for pending approvals {: #reminders-send :}

You can configure the Approvals bot to send reminders to your designated approvers on a scheduled basis. 

Reminders contain the requester, date of request, and application requested.

---

### View a dashboard overview of all requests for approvals {: #dashboard-overview :}

The Approval Bot provides approvers you designate with a default dashboard overview of all approval requests. Approvers can process requests from the dashboard.

The overview contains a list of all pending requests and includes the date of the request, the requested application, a description, and the requester's name.