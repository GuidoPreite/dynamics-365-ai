---
title: "Export a segment | MicrosoftDocs"
description: 
ms.custom: ""
ms.date: 04/01/2019
ms.reviewer: ""
ms.service: dynamics-365-ai
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
applies_to: 
  - "Dynamics 365 (online)"
  - "Dynamics 365 Version 9.x"
ms.assetid: 83200632-a36b-4401-ba41-952e5b43f939
caps.latest.revision: 31
author: "jimholtz"
ms.author: "jimholtz"
manager: "kvivek"
---
# Export a segment

[!INCLUDE [cc-beta-prerelease-disclaimer](../includes/cc-beta-prerelease-disclaimer.md)]

Now that you have created one or more segments using the **Segment builder** screen, you are ready to start acting upon your data. Make sure to first visit the [**Segments** section](pm-segments.md) if you haven't done so. 

At present, you can export any of your segments to both a CSV. file and a Dynamics 365 for Sales location. In the future, we will add additional segment export options.

1. Both options are available within the **Segments** page.
      
   - First, select (...) within a specific segment's tile.
   - Then, select the **Export** option from the actions menu.
   - Lastly, choose between a CSV format and a specific Dynamics 365 for Sales destination (only the Dynamics 365 for Sales destinations are highlighted below) 
      
   > [!div class="mx-imgBorder"] 
   > ![](media/segmentation-export-destination3.png "Segmentation destination")
      
   Note that you will not see any Dynamics 365 destinations until you add them using the **Export Screen** as explained in the sub-section below. This screen is accessible via the **Export Segment** tab on the left-side menu (under **Admin**).
      
2. The CSV option is also available in the specific segment's page by selecting **Export** at the top-right corner of the page.

   > [!div class="mx-imgBorder"] 
   > ![](media/segment-menu-export-top.png "Export segment")
    

## Adding a segment export destination

1. Within the **Segment Export** page, select **Add Destination**.

   > [!div class="mx-imgBorder"] 
   > ![](media/segmentation-add-destination.png "Segmentation add destination")

2. Give your destination a recognizable name, define its URL, and then select a Dynamics 365 for Sales account.

   > [!div class="mx-imgBorder"] 
   > ![](media/segmentation-export-destination.png "Segmentation export destination")

3. Upon the completion of Step 3, your destination should appear in the **Destinations** table. Below you can see an example with three created destinations. Beyond the details completed in Step 2, this table also specifies the creation date and time for your destinations.

   > [!div class="mx-imgBorder"] 
   > ![](media/segmentation-export-destination2.png "Segmentation add destination")
    
   Your saved destination will also appear in the **Segments** page under the export option we explored earlier.
   
   > [!div class="mx-imgBorder"] 
   > ![](media/segmentation-export-destination3.png "Segmentation destination")
    
   Upon clicking your Dynamics 365 for Sales destination, you should wait until the exporting process has completed. As long as it's in progress you can expect to see the following message.
  
   > [!div class="mx-imgBorder"] 
   > ![](media/segmentation-export-in-process.png "Segmentation export in process")

## View segments you have exported

That can be done in the **Segment Export** page. Below the **Destinations** table you can find another table, called **Exported Segments** which specifies important information around the segments you have exported.
    
> [!div class="mx-imgBorder"] 
> ![](media/segmentation-export-segments.png "Segmentation export segments")

## Delete a destination

That can be done via **Delete** in the **Segment Export** page.
