---
title: "Configure predefined Replication alerts (SSMS)"
description: Learn how to configure predefined replication alerts using SQL Server Management Studio (SSMS).
ms.custom: seo-lt-2019
ms.date: "03/14/2017"
ms.service: sql
ms.reviewer: ""
ms.subservice: replication
ms.topic: conceptual
helpviewer_keywords: 
  - "alerts [SQL Server replication]"
  - "predefined replication alerts [SQL Server replication]"
ms.assetid: c0414147-7ffe-4f9a-908c-71c1b5201584
author: "MashaMSFT"
ms.author: "mathoma"
monikerRange: "=azuresqldb-mi-current||>=sql-server-2016"
---
# Configure Predefined Replication Alerts (SQL Server Management Studio)
[!INCLUDE[applies-to-version/_ssnoversion.md](../../../includes/applies-to-version/sqlserver.md)]
  Replication offers the following predefined alerts, which can be configured to respond to replication events:  
  
-   **Replication: agent success**  
  
-   **Replication: agent failure**  
  
-   **Replication: agent retry**  
  
-   **Replication: expired subscription dropped**  
  
-   **Replication: Subscription reinitialized after validation failure**  
  
-   **Replication: Subscriber has failed data validation**  
  
-   **Replication: Subscriber has passed data validation**  
  
-   **Replication: agent custom shutdown**  
  
 Configure these alerts from the **Alerts** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or the **Warnings** tab in Replication Monitor. For more information about accessing this tab, see [View information and perform tasks using Replication Monitor](../../../relational-databases/replication/monitor/view-information-and-perform-tasks-replication-monitor.md).  
  
 In addition to these alerts, Replication Monitor provides a set of warnings and alerts related to status and performance. For more information, see [Set Thresholds and Warnings in Replication Monitor](../../../relational-databases/replication/monitor/set-thresholds-and-warnings-in-replication-monitor.md). You can also define alerts for other replication events using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] alerts infrastructure. For more information, see [Create a User-Defined Event](../../../ssms/agent/create-a-user-defined-event.md).  
  
### To configure a predefined replication alert in Management Studio  
  
1.  Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.  
  
2.  Expand the **SQL Server Agent** folder, and then expand the **Alerts** folder.  
  
3.  Right-click a replication alert, and then click **Properties**.  
  
4.  Set options in the **\<AlertName> alert properties** dialog box:  
  
    -   On the **General** page, click **Enable**; specify which database the alert should apply to.  
  
    -   On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.  
  
         If the alert is **Replication: Subscriber has failed data validation**, you can specify the response job that replication provides for this alert: Select **Execute job**, and then click the browse button (**...**). In the **Locate Job** dialog box, click **Browse**. In the **Browse for Objects** dialog box, select **Reinitialize subscriptions having data validation failures**. Click **OK** in both open dialog boxes. When the job executes, it uses a remote procedure call (RPC) to a stored procedure that reinitializes the subscription. If the Publisher uses a remote Distributor, you must define a remote server login at the Publisher, so that the RPC from the Distributor to the Publisher can be made.  
  
    -   On the **Options** page, customize the text of the response.  
  
5.  Select **OK**.

### To configure an alert for a threshold in Replication Monitor  
  
1.  On the **Warnings** tab click **Configure Alerts**.  
  
2.  In the **Configure Replication Alerts** dialog box, select an alert, and then click **Configure**.  
  
3.  Set options in the **\<AlertName> alert properties** dialog box:  
  
    -   On the **General** page, click **Enable**; specify which database the alert should apply to.  
  
    -   On the **Response** page, specify whether an e-mail should be sent and/or a job should be executed.  
  
         If the alert is **Replication: Subscriber has failed data validation**, you can specify the response job that replication provides for this alert: Select **Execute job**, and then click the browse button (**...**). In the **Locate Job** dialog box, click **Browse**. In the **Browse for Objects** dialog box, select **Reinitialize subscriptions having data validation failures**. Click **OK** in both open dialog boxes. When the job executes, it uses a remote procedure call (RPC) to a stored procedure that reinitializes the subscription. If the Publisher uses a remote Distributor, you must define a remote server login at the Publisher, so that the RPC from the Distributor to the Publisher can be made.  
  
    -   On the **Options** page, customize the text of the response.  
  
4.  Select **OK**.
  
5.  Click **Close**.  
  
## See Also  
 [Use Alerts for Replication Agent Events](../../../relational-databases/replication/agents/use-alerts-for-replication-agent-events.md)  
  
