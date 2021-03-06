---
title: "Connect Market Insights to Dynamics 365 | Microsoft Docs"
description: "Learn how to set up the connection between Market Insights and Dynamics 365."
keywords: "connect, connection, integration, dynamics 365"
ms.date: 10/31/2018
ms.service: dynamics-365-ai
ms.topic: article
ms.assetid: 757bbf6c-f4aa-410a-9c70-30093311c05a
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.custom: dyn365-ai-marketinsights
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365SE
---

# Connect Dynamics 365 and [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)]

(This topic is pre-release documentation and is subject to change.)

Set up the connection between [!INCLUDE[pn_dynamics_crm](../includes/pn-dynamics-crm.md)] and [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)] so you can link social posts to [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)]. Linking posts to [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] lets you create [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] records from social posts that were found in [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)] by using the **Automatic Record Creation and Update Rules** feature in [!INCLUDE[pn_dynamics_crm](../includes/pn-dynamics-crm.md)].  
  
## Prerequisites to establish a connection with Dynamics 365 

The following prerequisites apply to both [!INCLUDE[pn_dynamics_crm_online](../includes/pn-dynamics-crm-online.md)] and [!INCLUDE[pn_dyn_365_op](../includes/pn-dyn-365-op.md)]. Prerequisites specific to [!INCLUDE[pn_dynamics_crm_online](../includes/pn-dynamics-crm-online.md)] or [!INCLUDE[pn_crm_2016](../includes/pn-crm-2016.md)] are listed later in this topic.  
  
- You have a license assigned for [!INCLUDE[pn_dynamics_crm](../includes/pn-dynamics-crm.md)] and access to [!INCLUDE[Dynamics 365 Market Insights](../includes/pn-market-insights-long.md)].  
  
- You have a System Administrator security role in [!INCLUDE[pn_dynamics_crm](../includes/pn-dynamics-crm.md)]. [Contact your system administrator](https://go.microsoft.com/fwlink/p/?LinkID=513070) if you need an upgrade to your licensed products or an update to your permissions.
  
- You have an Administrator user role in [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)]. To find out your user role in [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)], go to **Settings** > **Personal Settings** > **Your Preferences**.
  
- Your browser is likely to block any pop-up windows opened by [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)] when authenticating to [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)], [!INCLUDE[tn_twitter](../includes/tn-twitter.md)], or [!INCLUDE[tn_facebook](../includes/tn-facebook.md)]. [Learn more about the recommended browser settings to manage authentication pop-up windows](system-browser-settings.md).
  
### Additional prerequisites to connect with Dynamics 365 (online)  
  
- Your [!INCLUDE[pn_dynamics_crm_online](../includes/pn-dynamics-crm-online.md)] instance is upgraded to [!INCLUDE[pn_crm_online_2015_update_1](../includes/pn-crm-online-2015-update-1.md)] or a later release.  
  
- Your [!INCLUDE[pn_dynamics_crm](../includes/pn-dynamics-crm.md)] instance is ready to receive social data. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [TechNet: Control social data](https://go.microsoft.com/fwlink/p/?LinkId=723352)  
  
### Additional prerequisites to connect with Dynamics 365 (on-premises) (IFD-enabled)
  
- You have upgraded to at least [!INCLUDE[pn_crm_2016](../includes/pn-crm-2016.md)] (on-premises) and the deployment is IFD-enabled.  
  
- Your [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] (on-premises) instance is an [!INCLUDE[pn_Internet_facing_deployment](../includes/pn-internet-facing-deployment.md)] with a public IP address.   
  [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [TechNet: Configure IFD for Microsoft Dynamics CRM](https://go.microsoft.com/fwlink/p/?LinkId=723354)  
  
- Enable OAuth support by following the [post-installation and configuration guidelines for Microsoft Dynamics CRM](https://go.microsoft.com/fwlink/p/?LinkID=723355).  
  
- Register your [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)] solution so that it can connect to and authenticate with the [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] server, and access the web services. Each solution that you want to connect with [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] (on-premises) (IFD-enabled) should be registered as a RedirectUri. Use the following command to register with the desktop client:  
  
  `Add-AdfsClient -Name Market_Insights -ClientId e8ab36af-d4be-4833-a38b-4d6cf1cfd525 -RedirectUri @("https://mi.ai.dynamics.com/api/connect/version/1.0/solutions/<solution id>/crm/oauthRedirect ", "https://mi.ai.dynamics.com/api/connect/version/1.0/solutions/<solutionid>/crm/oauthRedirect") -Description "OAuth 2.0 client for Market Insights".`  
  
  [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [TechNet: Walkthrough: Register a CRM app with Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=723356)  
> [!NOTE]
> The **Link to Dynamics 365** feature doesn't support [!INCLUDE[pn_crm_2016](../includes/pn-crm-2016.md)] (on-premises) in combination with the [!include[](../includes/pn-internet-explorer.md)] or [!include[](../includes/pn-microsoft-edge.md)] browsers.
  
## Establish a connection between [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)] and Dynamics 365

To connect [!INCLUDE[pn_dynamics_crm_online](../includes/pn-dynamics-crm-online.md)] and [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)], both services must be part of the same organization's [!INCLUDE[pn_Office_365](../includes/pn-office-365.md)] subscription. If you have licenses assigned to both [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] and [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)], you'll find both products in the [!INCLUDE[pn_Office_365](../includes/pn-office-365.md)] app launcher. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [Meet the Office 365 app launcher](https://go.microsoft.com/fwlink/p/?LinkID=401421)  
  
### Connect [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)] and Dynamics 365
  
1. In [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)], go to **Settings** > **Connections** > **Microsoft Dynamics 365**.  
  
2. Click **Add connection** ![add button](media/add-icon.png "Add button").  
  
3. Select the **Connection type** from the drop-down list.  
   ![add connection drop-down list in market insights](media/dynamics-365-connection-drop-down-menu.png "Add connection drop-down list in Market Insights")  
  
4. Provide the connection information for your [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] instance.  
  
   - **[!INCLUDE[pn_dynamics_crm_online](../includes/pn-dynamics-crm-online.md)]**
   - Select **Dynamics 365 (online)** and then click **Check Instances**  to automatically discover all available [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] instances in your [!INCLUDE[pn_Office_365](../includes/pn-office-365.md)] tenant.  
     ![add connection dialog box in market insights](media/add-connection-details-dialog-box.png "Add connection dialog box in Market Insights")  
  
   - Select the [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] instance you want to connect to from the list of discovered [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] instances for the selected location. For more information about the discovery process, see [Discover the URL for your organization using the Web API](https://msdn.microsoft.com/library/mt607485.aspx).  
  
   - Based on the selected [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] instance, the value in the **Name** field changes. You can update the [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] name if required.  
    
   - **For [!INCLUDE[pn_dynamics_crm](../includes/pn-dynamics-crm.md)] (on-premises)**
   - Select **Dynamics 365 (On-Premises)** and add the details of your [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] instance and enter a unique name for the connection.  
     ![on-premises](media/add-dynamics-365-connection.png "on-premises")")  
  
5. Click **Next** ![next button](media/next-icon.png "Next button").  
  
6. If the connection was successful, the **Dynamics 365 Instance** pane opens and shows you the details about the connected instance.  
  
7. You can set the **Set as default** control to ON to have this instance selected by default when creating new links to [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] records from social posts.  
  
8. If you changed a value in the **Dynamics 365 Instance** pane, click **Save** ![save button](media/save-icon.png "Save button") to apply your changes.  
   The connected [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] instance is now listed in the main pane when you go to **Settings** > **Connections** > **Microsoft Dynamics 365**.  
  
## Next steps

Now that you've connected [!INCLUDE[pn_dynamics_crm](../includes/pn-dynamics-crm.md)] and [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)], you can [define entity details](manage-connection-dynamics-365-record-creation.md) in [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)] to specify information for the Social Activity entity that is created when you link a post to [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)]. 
  
 When you are satisfied with the configuration of the entities, configure the **Record Creation Rules** in [!INCLUDE[pn_dynamics_crm](../includes/pn-dynamics-crm.md)] to automatically create [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] [records from Social Activity entities](create-dynamics-365-record-from-social-post.md).
   
## Privacy notice

[!INCLUDE[cc_privacy_mse_post_and_automation_rules](../includes/cc-privacy-market-insights-post-and-automation-rules.md)]  
  
### See also

[Link posts from Market Insights to Dynamics 365](link-posts-to-dynamics-365.md)   
[Create a Dynamics 365 record from a social post](create-dynamics-365-record-from-social-post.md)   
[Manage the connection between Dynamics 365 and Market Insights](manage-connection-dynamics-365-record-creation.md)   
[Administer Market Insights](settings-administration.md)
