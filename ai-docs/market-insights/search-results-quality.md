---
title: "Manage the quality of your search results in Market Insights | Microsoft Docs"
description: "Learn how to increase the quality of your search results."
keywords: "block content, block authors"
ms.date: 02/07/2019
ms.service: dynamics-365-ai
ms.topic: article
ms.assetid: 2225bfca-81ab-4053-be84-959cd0fb4e14
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

# Manage the quality of your search results

(This topic is pre-release documentation and is subject to change.)

As an Administrator or a Power Analyst, you can add terms to the list of blocked content to delete the matching posts in your analysis, or block entire domains from the data acquisition and delete already-acquired posts from these domains. Deleted posts are deducted from your monthly post quota.  
  
## Block domains from your sources  
To improve the quality of your organization’s data, you can block URLs that aren’t required. You can add URLs and partial URLs to a blocked sources list that will be excluded from data acquisition and analysis.  
  
### Block a domain
  
When you’re not interested in posts from a specific domain, add the domain to the list of blocked sources.  
  
> [!WARNING]
>  Blocking a top-level domain also excludes all of its subdomains. For example, if you exclude `contoso.com`, the subdomain `shop.contoso.com` is also excluded.  
>  When you add a domain to the list of blocked domains, posts from this domain will be hidden in Analytics for four hours and be irreversibly deleted afterward.  
  
1.  Go to **Search setup** > **Blocked Content**.  
  
2.  In the **DOMAINS** pane, enter the domain or partial domain in the field.  
  
3.  Click the **Add** button ![new or add button](media/plus-icon.png "New or Add button").  
  
### Remove a domain from the list of blocked sources  

Reactivate the data acquisition from a blocked source by removing the domain from the list.  
  
1.  Go to **Search setup** > **Blocked Content**.  
  
2.  Find the source you want to remove from the list and re-enable for data acquisition, and then click the **Delete** button ![delete button](media/trashbin-icon.png "Delete button").  
  
3.  In the confirmation message, click **CONFIRM**.  
  
4.  The data acquisition for the selected domain will restart.  
  
## Block keywords and terms from your searches  
 Exclude a specific term (word or phrase) by adding it to the blocked content list. Terms on the blocked content list cause matching posts to be deleted from the database. Because terms on the blocked content list act as a global exclusion, it’s a very efficient way to improve the quality of your data. However, be cautious of unintentionally deleting relevant posts.  
  
 Posts that don't show up in Analytics because of your blocked content settings don't count toward your post quota.  
  
 For example, if you’re listening to multiple search topics about cars, but don’t want to see any posts that mention the keyword “insurance,” you can add this term to the blocked content list. This deletes all posts that mention “insurance,” and posts that contain this term are no longer acquired by your search topics.  
  
### View excluded keywords  
 Every user can review the list of blocked content to find out which words or phrases are blocked from data acquisition.  
  
1.  Go to **Search setup** > **Blocked Content**.  
  
2.  Review the list of excluded keywords below the text input field.  
  
### Block keywords from your search results  
 Acting as global exclusions, keywords and phrases you add to the list of blocked content will be deleted from your analysis, and already-acquired posts  removed from the database.  
  > 
> [!IMPORTANT]
>  When you add a keyword to the list of blocked keywords, posts matching this keyword will be hidden in Analytics for four hours and be irreversibly deleted  afterward.  
  
1.  Go to **Search setup** > **Blocked Content**.  
  
2.  Type the term in the input field.  
  
3.  Click the **Add** button ![new or add button](media/plus-icon.png "New or Add button").  
  
### Remove a keyword from blocked content  
Remove a global exclusion and restart the data acquisition for posts matching this keyword by removing a keyword from the blocked content list. Data acquisition restarts after removing a keyword from the list of blocked content. Posts aren’t acquired retroactively.  
  
1.  Go to **Search Setup** > **Blocked Content**.  
  
2.  Identify the list entry you want to remove from the blocked content, and then  click the **Delete** button ![delete button](media/trashbin-icon.png "Delete button").  
  
3.  In the confirmation message, click **CONFIRM**.  
  
## Manage the data acquisition volume  
  
- Optimize your search topics regularly. Review the rules to make sure that only relevant data is selected. Validate your rules before saving the search topic to get an idea of how many posts you’re expecting for the configuration you provided.  
  
- Maintain a list of blocked sources to delete matching posts and avoid any posts appearing in your results from the listed domains. When you add a source to the list of blocked sources, posts from this source will be hidden in Analytics for four hours and be irreversibly deleted afterward.  
  
- Maintain a list of blocked terms to delete matching posts and avoid any posts appearing in your results that match the listed terms. When you add a term to the list of blocked terms, posts matching this term will be hidden in Analytics for four hours and be irreversibly deleted afterward.  
  
- Exclude authors who publish irrelevant posts that match one of your search topics.  
  
### Privacy notice  
 [!INCLUDE[cc_privacy_msl_social_services_content](../includes/cc-privacy-market-insights-social-services-content.md)]  
  
### See Also  
 [Set up searches to listen to social media conversations](set-up-searches.md)   
 [Refine your search rules](refine-search-rules.md)
 
