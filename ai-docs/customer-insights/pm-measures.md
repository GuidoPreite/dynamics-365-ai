---
title: "Measures | MicrosoftDocs"
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
# Measures

The **Measures** page enables you to define all the key performance indicators (KPIs) that best reflect the performance and health of your specific business. You can define customer-related measures such as Lifetime Value and business-health measures such as Monthly Active Users. Customer Insights provides an intuitive experience for building different types of measures, with a query-builder wizard that doesn’t require you to manually code or validate a query. 

Once you define measures, you can benefit in a variety of ways. For example:

- Track business measures on your home page.
- View measures for a specific customer as part of the **Customer Card**. See the **Customer Card Add-in** section to learn more.
- Use measures to define a customer segment using the **Segment Builder** page. See the **Segments** section to learn more.

## Step One: Choose a measure type

**Customer Insights supports three types of measures:**

- **Customer attribute**: This measure is a single field per customer that reflects a score, value, or state for the customer. Customer attributes are created as attributes in a new system-generated entity called **Customr_Measure.** (can be viewed on the **Entities** page). Examples are *Lifetime Value* and *Total Sales*.

 > [!div class="mx-imgBorder"] 
 > ![](media/measures-customer-entity.png "Customer_Measure attribute")

- **Customer measure**: This measure provides input on customer behavior with breakdown by dimensions. A new entity is generated for each measure, with potential multiple records per customer. Examples: Number of visits per channel and Total sales per day.
- **Business measure**: This measure helps you track your business performance and health. Examples: Average sales per customer and Monthly Active Users (MAU).

There are two possible outputs for a business measure:
 - A single-number measure that displays on the home page.
 - A new entity.

Later we show how to create these outputs.

- **Customer Measure**: This measure provides input on customer behavior with breakdown by dimensions. A new entity will be generated per measure (can be viewed on the **Entities** page), with potential multiple records per customer. Examples: *Number of visits per channel* and *Total sales per day*.
- **Business Measure**: This measure helps you track your business performance and health. Examples: *Average sales per customer* and *MAU*. Can be created either as a single-number measure that will show up on the **Home** page (default state), or as an entity once one a dimension is added to it (new entity will show up in the **Entities** page).

To begin defining a measure, from the **Measures** page, select **Add New Measure**:

> [!div class="mx-imgBorder"] 
> ![](media/search-measures.png "Search measures")

## Step Two: Choose the starting entity

Selecting **New Measure** opens the measure creation pane. 

For the **Business Measure** option, you will see the **New business measure** pane:

> [!div class="mx-imgBorder"] 
> ![](media/new-business-measure.png "New business measure")

- **Name** (mandatory): After completing the configuration of your measure, it appears on the **Measures** page under this name.
- **Display name** (optional): As mentioned earlier, your measure is added as an attribute or saved as a new entity. In both cases, the measure carries over the Display Name to the home page and Customer Card.
- **Starting entity** (mandatory): Choose the entity you wish to build your measure around. For example, if we might choose an *Orders* entity as a starting entity if our measure is *Average order amount*. If you want to include fields from multiple entities in your measure fields, choose any of these entities.  

You see the **New profile measure** pane when you select the **Customer Measure** option:

> [!div class="mx-imgBorder"] 
> ![](media/new-profile-measure.png "New profile measure")

This pane is similar to the one you see when you select the **Business Measure** option, except for one difference: The Customer Profile entity is automatically selected as your starting entity. This default selection can't be changed.

You see the **New profile attribute** pane when you select the **Customer Attribute** option:

> [!div class="mx-imgBorder"] 
> ![](media/new-profile-attribute.png "New profile attribute")

## Step Three: Choose related entities

After completing Step Two, you'll see the following page:

> [!div class="mx-imgBorder"] 
> ![](media/measure-definition.png "Measure definition")

Customer Insights lets you build measures by leveraging data from multiple data sources that are now connected through the Customer entity. At this point, you should decide whether additional entities are needed as part of your measure definition. 

One use case might be creating an expression that is based on attributes from two or more different entities (see Step Four).  Another use case, specifically for the customer measure and business measure, is creating a measure entity that is composed of multiple entities (see Step Five). 

In order to choose additional entities, select **Add new entity**, and choose the entities you want.

> [!div class="mx-imgBorder"] 
> ![](media/select-an-entity.png "Select an entity")

>[!NOTE]
> You can select only those entities that have relationships to your starting entity. If you haven't defined relationships yet, see the **Relationships** section. 

## Step Four: Calculate a variable
In Customer Insights, variables are calculations that are made on each of your selected fields' records. For example, summing point-of-sale (POS) and online sales for each of your customers records. 

Steps for defining a variable: 

Select **New Variable**:

> [!div class="mx-imgBorder"] 
> ![](media/accounts-dynamics-365.png "Accounts Dynamics365")

This opens the **New variable** pane.

> [!div class="mx-imgBorder"] 
> ![](media/new-variable-name.png "New variable name")

Complete these steps:

1. Give the variable a recognizable name. 
2. Select the **Expression** area.
3. Choose a field from the list of fields to the right of the **Expression** area to begin your calculation with.
4. Type an expression in the **Expression** area while choosing more fields to be included in your calculation.

   >[!NOTE]
   >Currently, Customer Insights supports arithmetic expressions only. Moreover, at present variable calculation is not supported for entities from different entity-paths (visit the **Relationships** section to learn more on what is considered to be an "entity path").

5. Select **Done**.

In the following example, we have defined a calculation for the relative contribution of a single purchase to the Customer Lifetime Value (CLTV).

> [!div class="mx-imgBorder"] 
> ![](media/new-variable-name2.png "New variable name")

## Step Five: Define your Measure entity or attribute

In this step, you will decide how to aggregate and summarize your chosen entities and calculated variables into a Measures entity or attribute. 

**Step 1: Defining first dimension**

What is a dimension? You can think of a dimension as a “group by” function: The data within your new Measure entity or attribute will 
be grouped by all of your defined dimensions.

In the following example, we have defined **State** as the dimension field of the **BusinessReport: Customer 360** Measure entity. On the screen, we can see that the data we included in that entity (first highlighted column) is grouped by the State column (second highlighted column).

> [!div class="mx-imgBorder"] 
> ![](media/measures-businessreport-data-tab.png "Entity grouped by State")

Select or enter the following information as part of your dimension's definition:

> [!div class="mx-imgBorder"] 
> ![](media/measure-definition2.png "Measure definition")

**Entity/variable**: If you define a Measure entity, it should include at least one attribute. If you define a Measure attribute, it will include only one attribute by default. This selection is about choosing the entity that includes that attribute. <br />
**Field**: Choose the specific attribute to be included either in your Measure entity or attribute. <br />
**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis. This is a required selection only if you have selected a Date type of attribute. 

> [!div class="mx-imgBorder"] 
> ![](media/measures-businessreport-measure-definition2.png "Measure definition")

**As**: Defines the name of your new field in the Measure entity or attribute. <br />
**Display Name**: Defines the display name of your field in the Measure entity or attribute.

>[!NOTE]
>Your Business measure will be saved as a single-number entity and will appear on the home page unless you complete Step 2 below (adding more dimensions to your measure). If you complete Step 2, the measure will **not** show up on the home page.
  
**Step 2 (optional)**: Add more dimensions by selecting **Add new dimension** and making the same selections we have just illustrated.

> [!div class="mx-imgBorder"] 
> ![](media/new-dimension.png "New dimension")

**Step 3 (optional)**: Add aggregate functions 

Any aggregation that you create results in a new value within your Measures entity or attribute. 
Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** and **Last**.
Note: 
- Under the **Last** operator, the last record that was added to each dimension value will be taken. For example, if the dimension is CustomerID and the Last operator is applied on a Sales attribute, the result will be the last sales record for each CustomerID.
- Under the **First** operator, the first record will be taken for each dimension value.


For example, let's assume that we have added the aggregated value **Average Service Amount**, which takes the average of every **Service Amount** field within the entity **Service: Orders** and averages it:

> [!div class="mx-imgBorder"] 
> ![](media/measures-aggregated-field-example.png "Aggregated field example")

When visiting the **Entities** page and choosing the new measure we have just created (called **AggregatedFieldExample**), we can see that our aggregation formula has created the new value **Average Service Amount**.

> [!div class="mx-imgBorder"] 
> ![](media/measures-aggregated-field-example2.png "Aggregated field example")

Let's explore the steps involved in defining a new value.

 1. First, select **New value**.

   > [!div class="mx-imgBorder"] 
   > ![](media/measure-definition3.png "Measure definition")

 2. Then, make your selections.

   > [!div class="mx-imgBorder"] 
   > ![](media/measure-definition4.png "Measure definition")

   - **Function**: At present, we support **Sum**, **Min**, **Max**, **Count** and **Unique Count** as aggregation options. <br />
   - **Entity/Variable**: Choose the entity that includes the attribute on which you want to base your calculation. You can also choose a variable if you created one as part of Step Four. <br />
   - **Field**: Choose the specific attribute or variable on which you want to base your calculation. <br />
   - **As**: Your calculation will result in a new value. Define the name of your new value in the Measures entity/attribute. <br />
   - **Display Name**: Define the display name of your new value in the Measures entity/attribute.

 3. Save your measure.

    > [!div class="mx-imgBorder"] 
    > ![](media/measure-definition-save.png "Measure definition")

## View your measures 

Once you have completed your first measure, you'll see the following page summarizing your created measures.

> [!div class="mx-imgBorder"] 
> ![](media/new-measure.png "New measure")

As mentioned before, you can also view your created measure in one of the folloiwng ways:
- If created a **Customer measure**, you can view your new measure entity on the **Entities** page.  
- If created a **Customer attribute**, you can view your new attribute on the **Entities** page - look for the *Customer_Measure* entity.
- If created a **Business measure** with no dimensions, you can view your created measure on **Home** page (under *Insights* section). 
- Lastly, if you created a **Business measure** with one or more dimensions, you can find your new measure entity on the **Entities** page. 

## Add and Edit measures
At any time, you can create a new measure by selecting **Add Measure** as discussed earlier.

You can also edit, delete, or rename the data of any of your created measures by first selecting the following **(three dots)** button:

> [!div class="mx-imgBorder"] 
> ![](media/measure-menu.png "Measure menu")

Choose from the **Options** drop-down menu.

> [!div class="mx-imgBorder"] 
> ![](media/measure-menu2.png "Measure menu")

Here is an example of the **Rename measure** window.

> [!div class="mx-imgBorder"] 
> ![](media/rename-measure.png "Rename measure")

## Next step
Make sure to visit the **Unify** section if you haven't yet completed the data configuration process. Upon the completion of the Unify modules, you might want to use the measure you have just created to create your first customers' segment using the **Segments** page. You can also unlock more insights via the **Activities** and **Enrich Profiles** pages.

