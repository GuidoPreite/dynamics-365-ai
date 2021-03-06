---
title: "Understand user roles in Market Insights | Microsoft Docs"
description: "Understand the permissions for the available user roles in Market Insights."
keywords: "permissions, user roles, interaction role, configuration role"
ms.date: 10/31/2018
ms.service: dynamics-365-ai
ms.topic: article
ms.assetid: ef77beed-3bb7-4a65-876a-57bcf2ae2d15
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

# Understand user roles


(This topic is pre-release documentation and is subject to change.)

Administrators can assign roles with appropriate permissions for your [!INCLUDE[Dynamics 365 Market Insights](../includes/pn-market-insights-long.md)] solution users. Every user can be assigned two sets of roles: configuration roles and interaction roles. This gives administrators flexibility to manage user roles and permissions, and to give users the functionality they need.  

Every invited user should be assigned both types of roles.  

An administrator can update the automatically assigned Power Analyst and Responder role for a newly invited user.

To assign and edit user roles, go to **Settings** > **User Management**.  

> [!IMPORTANT]
>  User roles set in [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] don’t apply to [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)]. You’ll need to set roles in both [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)] and in [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)]. A user can have a different role in each solution.  
> 
>  If there are **Newly invited** users in the solution, administrators can find them from the drop-down menu on **Settings** > **User Management**.  

## Configuration user roles  

The configuration role defines permissions to set up search topics and to configure the application.  

The following table shows the Analyst, Power Analyst, and Administrator configuration roles and their permissions.  

|Permissions|Analyst|Power Analyst|Administrator|  
|-----------------|-------------|-------------------|-------------------|  
|[View all analysis](analyze-social-data-using-widgets.md)|Yes|Yes|Yes|  
|[Edit sentiment value](work-with-posts.md)|Yes|Yes|Yes|  
|[Delete posts](work-with-posts.md)|No|Yes|Yes|  
|[Exclude/delete authors](manage-authors.md)|No|Yes|Yes|  
|[Create and edit search topics](set-up-searches.md)|No|Yes. Can only edit self-created search topics|Yes|  
|[Create and manage categories](search-topic-categories.md)|No|Can only edit owned categories|Yes|  
|[Manage custom sources](custom-sources.md)|No|No|Yes|  
|[Create and edit location groups](manage-global-settings.md)|No|Can only edit owned location groups|Yes|  
|[Manage user roles](assign-user-roles.md)|No|No|Yes|  
|[Exclude sources and terms](search-results-quality.md)|No|No|Yes|  
|[Set up and view connections to other apps](manage-connections.md)|No|No|Yes|  
|[Create and manage alerts](email-alerts.md)|Yes|Yes|Yes|  
|[Define global settings](manage-global-settings.md)|No|No|Yes|  
|[Create and edit activity maps](activity-maps.md)|Yes|Yes|Yes|  
|[Manage automation rules](automation-rules.md)|No|No|Yes|  
|[Promote custom tags to auto tags, rename custom tags, delete custom tags](tags.md)|No|No|Yes|  
|[Edit search topic owners](set-up-searches.md)|No|No|Yes|  

## Interaction user roles  

The interaction role defines permissions to collaborate with other solution users and to engage on social media from within the solution.  

To let users interact with a post from [!INCLUDE[Market Insights](../includes/pn-market-insights-short.md)], administrators can assign the appropriate interaction roles. Typically, a user with a Manager role defines streams and shares them with other users. Readers just want to keep track of the conversations and posts assigned to them, while Responders tend to take action on a post.  


|       Permissions                  | Reader | Responder | Manager |
|------------------------|--------|-----------|---------|
|  [View streams](social-center.md)          |  Yes   |    Yes    |   Yes   |
|  [Manage social profiles](manage-social-profiles.md)                       |   No   |    Yes    |   Yes   |
|  [Edit labels on posts](work-with-posts.md)                                 |   No   |    Yes    |   Yes   |
|  [Edit post assignments](work-with-posts.md)                              |   No   |    Yes    |   Yes   |
|  [Manage streams](social-center.md)                                    |   No   |    No     |   Yes   |
|  [React on a post](publish-react-posts.md)                                |   No   |    Yes    |   Yes   |
|  [Publish a new post](publish-react-posts.md)                          |   No   |    Yes    |   Yes   |
|  [Create a record from a social post](create-dynamics-365-record-from-social-post.md)        |   No   |    Yes    |   Yes   |
|  [Unlink a post](create-dynamics-365-record-from-social-post.md) from a [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] record |   No   |    No     |   Yes   |
|  [View record details](create-dynamics-365-record-from-social-post.md)            |  Yes   |    Yes    |   Yes   |
|  [View automation rules](automation-rules.md)                                  |  Yes   |    Yes    |   Yes   |
|  [Create custom tags](tags.md)                                                   |   No   |    Yes    |   Yes   |
|  [Edit tags](tags.md) on posts (confirm  tags, add tags, remove tags)             |  Yes   |    Yes    |   Yes   |
|  [Create new author tags](author-tags.md)                                       |   No   |    Yes    |   Yes   |
|  [Add existing author tags, change or remove author tags](author-tags.md)           |  Yes   |    Yes    |   Yes   |

### See also  
[Administer Market Insights](settings-administration.md)   
[Assign permissions and user roles](assign-user-roles.md)

