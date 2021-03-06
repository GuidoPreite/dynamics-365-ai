---
title: "Manage search topics in Market Insights | Microsoft Docs"
description: "Learn how to create a new search topic or delete an existing one in Market Insights."
keywords: "searches, search topic, search rules, gather data"
ms.date: 02/07/2019
ms.service: dynamics-365-ai
ms.topic: article
ms.assetid: 4e5937a9-3509-4d8f-b747-aa9601ee7e9d
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

# Create or delete a search topic

(This topic is pre-release documentation and is subject to change.)

It’s important to start with a clear idea of what kind of online information you want to listen to. Set up new search topics and add at least one rule to each of them to find out what your audience is discussing in their public social media posts. You can also edit search topics you’ve created or delete them if they are no longer relevant.  

  
## Create a search topic  

Users with at least Power Analyst permissions can create and edit search topics.
  
1. Go to **Search Setup**.  
  
2. In the **Search Topics** pane, click **Add Search Topic** ![add button](media/add-icon.png "Add button") to open the **New Search topic** page.  
  
3. Provide a name for your search topic in the **Name** text box and verify the category of your topic.  
  
   > [!NOTE]
   >  You can add search topic names that contain up to 35 characters. The search topic names are only for your reference; they aren’t included in the actual search. Search topic names are like titles for your search topics so you can quickly relate to and use or reuse them.  
  
4. If you want another user to be the owner of this search topic, click **Edit Owner** ![edit button](media/edit-icon.png "Edit button") next the search topic owner and enter the user name in the search box or click the name in the list below.  
  
5. Under **Rules**, click **Add Rule** ![add button](media/add-icon.png "Add button") to open the **Add Rule** page.  
  
6. Select the rule type you want to create, and then provide the required information. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [Find out what's covered by sources](sources-coverage.md)  
  
7. Click **Continue** to estimate the number of results and see a preview of posts matching this rule.  
  
8. Add another search rule to your topic (optional).  
  
9. In the **Search Topics** pane, click **Save** ![save button](media/save-icon.png "Save button") to store the search topic and start the data acquisition.  
  
    > [!NOTE]
    >  It will take some time for the first posts to be acquired for your newly-created topic. The delay also depends on how much volume your topic in general has. For example, a topic with high volume will give you results faster than a topic with lower volume. Make sure to check in Analytics and set your time frame to **Today** if you have set up a new topic and are expecting posts.  
  
## Edit a search topic  
To help you find relevant posts and be up to date with the business requirements, you can change your search topics and the associated rules at any time. We strongly recommend updating the rules in a search topic from time to time to make sure you’re gathering only relevant information.  
  
> [!NOTE]
>  Administrators can edit every search topic in the solution, while Power Analysts can only edit the search topics they own.  
  
1.  Go to **Search Setup**.  
  
2.  In the list of search topics, click the topic you want to edit.  
  
3.  In the list of rules, click the rule you want to edit.  
  
4.  Validate the updated rule, and then click **Save** ![save button](media/save-icon.png "Save button") to update the search topic.  
  
<a name="manage_ownership"></a>   
## Manage ownership of a search topic  
Administrators in your organization can change the owner of a search topic to ensure every search topic is owned by the appropriate user. Users with the Power Analyst role are only allowed to edit owned search topics, but Administrators can empower these users by giving them ownership of search topics they manage, or create a search topic on behalf of other users.  
  
1.  Go to **Search Setup**.  
  
2.  In the list of search topics, click  the topic you want to edit.  
  
3.  In the search topic settings pane, click **Edit Owner** ![edit button](media/edit-icon.png "Edit button") next the search topic owner.  
  
4.  Enter the user name in the search box or click the name in the list below it.  
  
5.  Click **Save** ![save button](media/save-icon.png "Save button") to update the search topic.  
  
## Delete a search topic  
  
> [!IMPORTANT]
>  As an Administrator, you can delete search topics at any time. Power Analysts can only delete search topics they own.  
  
1. Go to **Search Setup**.  
  
2. In the list of search topics, click the **Delete** button ![delete button](media/trashbin-icon.png "Delete button") by the topic you want to delete, and then confirm the deletion.  
  
   > [!NOTE]
   >  Deleting a search topic has the following effects:  
   > 
   > - Data acquisition for the deleted topic stops immediately.  
   >   - An automated email notification is sent to the user who created the search topic.  
   >   - The search topic is no longer visible in the user interface.  
   >   - Alerts and streams based on this topic are deactivated.  
   >   - The quota will remain the same even if the search topic has been deleted. You need to add the keywords contained in a deleted topic to the Block Content so your [deleted search topics will no longer affect the quota](manage-post-quota.md).  
  
### Privacy notices  
 [!INCLUDE[cc_privacy_msl_social_services_content](../includes/cc-privacy-market-insights-social-services-content.md)]  
  
 [!INCLUDE[cc_privacy_msl_index_cached_data](../includes/cc-privacy-market-insights-index-cached-data.md)]  
  
 [!INCLUDE[cc_privacy_mse_bing_social_check](../includes/cc-privacy-market-insights-bing-social-check.md)]  
  
### See Also  
 [Set up searches to listen to social media conversations](set-up-searches.md)   
 [Add rules to a search topic](add-rules-search-topic.md)
 
