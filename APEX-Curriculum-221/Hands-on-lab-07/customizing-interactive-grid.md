<!--# Create the shopping cart page -->
## Introduction

In this lab, you customize:
  - **Project Tasks** page we Created in Lab 5.
  - **Interactive Grid** Page both as a developer and an end user.

<!--
Customers will be able to:
- Review the items in the shopping cart
- Edit the quantity of the items
- Remove an item
- Clear the shopping cart
- Proceed to checkout

Estimated Time: 20 minutes

Watch the video below for a quick walk through of the lab.

[](youtube:Cvl9xMAqnm8)
-->
### Objectives
In this lab, you:
- Customise the Interactive Grid page you have created in **Demo Projects** Application both as a **Developer** and an **End-user**.

### Downloads

- Did you miss out trying the previous labs? Don’t worry! You can download the application from [here](Demo-projects2.sql) and import it into your workspace. To run the app, please run the steps described in **Hands-on-lab-01** and **Hands-on-Lab-02**.


## Task 1: Manage and Customize Interactive Grid as a Developer
This lab uses the **Demo Projects** application. In this lab, you customize the **Interactive Grid** for end users. You create column groups, set pagination type, and set the report downloadable formats that should be available for end users. You also enable end users to save the report as Public interactive grids and convert a read only interactive grid to an editable interactive grid.

1. Navigate to **App Builder** and run the **Demo Projects** application.

    ![](./images/select-demo-projects-app11.png " ")

    ![](./images/run-demo-projects-app11.png " ")

2. In the navigation menu, click **Projects Tasks**. You want to customise the display of this interactive grid for your end users. In the Developer Toolbar, click **Edit Page 4**.

    ![](./images/click-page11.png " ")

3. Add column group headers to the interactive grid as:
  - Project Breakdown: Project, Task_Name columns
  - Schedule: Start_Date, End_Date columns
  - Project Financing: Cost, Budget columns  

  a) In the page designer, under Components > Body, navigate to **Project Tasks** Interactive Grid region and right-click **Column Groups**. Select **Create Column Group**.

 ![](./images/create-column-group11.png " ")

  b) In the Property Editor, enter **Project Breakdown** for Heading.

 ![](./images/create-column-group1.png " ")

  c) Repeat the above two steps **a** and **b** to create column groups: **Schedule** and **Project Financing**.

  d) Now that you created column groups, you need to assign columns to them. Expand **Columns** and select **Project** and **Task_Name** columns.

  e) In the property editor, under **Layout**, select **Project Breakdown** for Group.

  ![](./images/select-project-breakdown11.png " ")

  f) Then, select **Start_Date** and **End_Date** columns. In the property editor, under **Layout**, select **Schedule** for Group.

  ![](./images/select-schedule-group11.png " ")

  g) Finally, select **Cost**, and **Budget** columns. In the property editor, under **Layout**, select **Project Financing** for Group.

  Then, click **Save** and **Run Page**.

  ![](./images/select-financing-group11.png " ")

  h) The interactive grid now displays column groups.

  ![](./images/display-groups11.png " ")

4. Rearrange the columns in the interactive grid. You want to display the column groups Project Breakdown, Schedule, and Project Financing display in order followed by Status and Assigned To.

  a) Hover the mouse over the Project Financing column group header to display the drag handle. Your mouse cursor also changes when it comes into contact with the drag handle. Click and hold the drag handle.

  b) Then, drag the column group to the Status column location. The heading shifts out of place in the row. The Project Financing column group should be followed by the Status column. Release the mouse. The Project Financing column group drops into place.

  ![](./images/rearrange-column11.png " ")

  ![](./images/rearrange-column12.png " ")

5. Click **Page n** in the runtime developer toolbar. You want to make **ID** Column as **Primary Key**. This will help you to make the Interactive Grid editable.

  ![](./images/define-primary-key.png " ")

6. You want to ensure that end users can save Public interactive grids. You want to exclude HTML from the download formats available to end users.
  a) Under Rendering, select the **Project Tasks** Interactive Grid region.

  ![](./images/select-project-tasks11.png " ")

  b) In the property editor, select **Attributes** , then navigate to **Enable Users To**. Click **Save Public Report** to enable the feature. Under **Download**, deselect the **HTML** check box.

  ![](./images/enbale-public-reports11.png " ")

7. Convert this read only interactive grid in to an **Editable interactive grid**. Then, reset the pagination as Page type displaying the total row count.  

  a) Under Rendering, select the **Project Tasks** Interactive Grid region.

  b) In the property editor, navigate to **Attributes** and then navigate to Edit. Click **Enabled**, to turn on the feature.
  Also Under **Pagination**, select **Page** for Type.

  ![](./images/edit-enabled11.png " ")

8.  Delete the column groups in the interactive grid. Under Rendering > Project Tasks Interactive Grid > Column Groups. Select **Schedule**, **Project Breakdown** and **Project Financing**, right-click and click **Delete**.

![](./images/delete-column-group11.png " ")

9. Suppose you want to display the ID column and exclude the ID column from DML operations. Under **Page Rendering > Project Tasks** Interactive Grid, expand Columns and select **ID**.    
Navigate to **Identification** and Set Type to **Display Only**, then Navigate to **Source** and Click on **Query Only** to enable.
Click **Save and Run Page**.
![](./images/set-id-col-attributes11.png " ")


## Task 2: Customize interactive grid as an end-user.
In this lab, you use and customize the display of your interactive grid. You also edit an editable interactive grid.

1. Notice that the interactive grid is editable now. You see the Edit, Save, and Add Row buttons. Also, the pagination type that you have set is displayed now. Perform a non-case-sensitive search for ‘**server**’ on the entire interactive grid.  
To do this, enter **server** in the search bar text area and click **Go**.

 ![](./images/search1.png " ")

2. Remove the filter by clicking the **X** icon.  
Now, in the search bar, click the **magnifying glass** and select **Task Name** column.

 ![](./images/search2.png " ")

3. Enter **server** in the text area and click **Go**. Notice that the search is now restricted only to the **Task Name** column.

  ![](./images/search3.png " ")

4. Remove the filter by clicking the **X** icon. You want to update the Cost for the Project with Id 1. Click the field and replace the existing value with **500**.

  ![](./images/search4.png " ")

5. The changes are not saved yet. Click the **Save** button.  
    The changes are saved now.

  ![](./images/search5.png " ")

6. You want to update another row. This time, click the Row Actions menu icon at the edge of the row for the project with Id **2** and select **Single Row View**.

  ![](./images/single-row-view.png " ")

7. You are now in the single row view of the project with Id **2**. Replace the existing value for Budget with **9000** and click **Save**. Then, click **Report View**.  

  ![](./images/single-row1.png " ")  

  The row now displays **9000** for Budget.

8. You want to create a control break on the Project column. Click **Actions > Format > Control Break**.

  ![](./images/set-control-break.png " ")

9. In the Control Break dialog, enter **Project** for Column and click **Save**.

  ![](./images/control-break1.png " ")

10. The control break is now applied. You want to highlight rows that meet a      condition. Select Actions > Format > Highlight.

  ![](./images/highlight1.png " ")

11. In the Highlight dialog, enter the following:
  - Name: Enter **Project Costing greater than 800**
  - Background Color: Click Colors and select **Yellow**.
  - Text Color: Click Colors and select **Red**.
  - Column: Select **Cost**
  - Operator: Select **greater than or equals**
  - Value: Enter **800**  

    Click **Save**.
    ![](./images/highlight2.png " ")

12. Notice the rows with cost greater than 800 are highlighted.

  ![](./images/highlight3.png " ")

13. You want to save the changes made to the interactive grid. Select **Actions** > **Report** > **Save As**.

  ![](./images/save-grid1.png " ")

14. In the Report – Save As dialog, select Private for Type. Enter **My Private Report** for Name. Click **Save**.

  ![](./images/save-report.png " ")


15. Notice that the Primary interactive grid and the interactive grid you saved now are available in the Reports drop down list.  
You want to return back to the Primary interactive grid. Click **Primary Report** in the Reports drop down list.

    ![](./images/select-primary-report.png " ")

16. You want to make few more customizations and save the interactive grid as another Private report. You do not want the **Start Date**, **End Date**, and **Assigned To** columns to be displayed in the report.
Click the **Start Date** column header and then click **Hide**.

    ![](./images/hide-column1.png " ")

  Similarly perform the same step for **End Date** and **Assigned To** column.

17. You want to add a chart to the interactive grid. Select **Actions** > **Chart**.

    ![](./images/chart1.png " ")

18. In the Chart dialog:
    - Type: Select **Bar**
    - Label: Select **Project**
    - Value: Select **Cost**
    - Aggregation: Select **Sum**  
    Click **Save**.
  ![](./images/chart2.png " ")

19. The chart is displayed. You want to save the customization made to the interactive grid. Select **Actions** > **Report** > **Save As**.

  ![](./images/save-report1.png " ")

20. In the Report – Save As dialog, select **Private** for Type. Enter **My Custom Report** for Name. Then, click **Save**.

  ![](./images/save-report2.png " ")

21. The report is now saved under Private in the Reports drop down list. Click the **Grid** icon.

  ![](./images/select-grid-icon.png " ")

22. You want to download the report. Select **Actions > Download**.

  ![](./images/download-report.png " ")

23.  Note that the **HTML** download option is no longer available. Select **Excel** and click **Download**.

  ![](./images/download-report1.png " ")

24. The report is now downloaded as **Excel**.

  ![](./images/downloaded-report.png " ")


## **Acknowledgments**

- **Author** - Roopesh Thokala, Product Manager
- **Contributors** - Roopesh Thokala, Product Manager
- **Last Updated By/Date** - Roopesh Thokala, Product Manager, April 2021
