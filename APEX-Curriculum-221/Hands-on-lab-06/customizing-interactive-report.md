# Customizing Interactive Reports

## Introduction

In this Hands-on-lab, you will Manage and Customise the Interactive report in the **Sample Reports** application both as an **End-user** and as a **Developer**.


### Objectives

In this lab, you:
- Customise the Interactive Report page you have have in **Sample Reports** Application both as a **Developer** and an **End-user**.


## Task 1: Customizing an Interactive report as an end-user.

 In this lab, you customize and use an interactive report as an end user.

 1. To start with, run the **Sample Reporting** application. Click **App Builder**.

  ![Select App Builder](images/navigate-to-app-builder.png " ")

2.  Navigate to **Sample Reporting** and then click **Run Application**.

  ![Navigate to Sample Reporting](images/navigate-to-sr.png " ")

  ![Run Application](images/run-application.png " ")

3. In the **navigation menu** or in the **Cards Region**, click **Interactive Report**.

  ![Navigate to Interactive Report](images/click-ir.png " ")

4. Suppose that you do not want to display the **Start Date** and **End Date** columns in the report. Also, you want the **Status** column to display just after the **Assigned To** column. Perform the following steps:  
  a) Click Actions and select Columns.

  ![Select Columns under Actions](images/select-columns.png " ")

  b) The **Select Columns** dialog appears. The columns on the right are displayed, and the columns on the left are hidden. Select **Start Date** and **End Date** in **Display in Report group**, and move the selected columns into the **Do Not Display** list by clicking the left arrow **<**.

  ![Select Columns1](images/select-columns1.png " ")

  c) You can reorder the displayed columns using the arrows on the far right.
  Select **Status** in the Display in Report group and click the Down arrow once. Then, click **Apply**.

  ![Select Columns2](images/select-columns3.png " ")

  ![Select Columns3](images/select-columns2.png " ")

  d) The interactive report is displayed with the changes made in the above steps.

  ![Run Interactive Report1](images/run-ir1.png " ")

5. Next, let's say you want to filter the report results. First, you want to filter the report to display rows which meet the criteria **Cost <= 2000**. Within these filtered results, you then create another filter to display rows with **Project is Bug Tracker**. Perform the following steps:  

  a) Click Actions and select Filter.

  ![Click Filter under Actions](images/select-filter1.png " ")

  b) For Filter Type, select Column. Select the following:
   - For **Column**, select **Cost**
   - For **Operator**, select **<=**
   - For **Expression**, enter **2000**   
  Then, click **Apply**.

  ![Create Filter1](images/create-filter1.png " ")

  c) Next, add the second filter on the **Project** column. Click the **Actions** menu and select **Filter**.

  ![Create Filter2](images/select-filter2.png " ")

  d) In the Filter Dialog, select the following:
   - For Column, select **Project**
   - For Operator, select **=**
   - From the Expression list, select **Bug Tracker**
  Click **Apply**.

  ![Create Filter3](images/create-filter2.png " ")

  ![Run Interactive Report2](images/run-ir2.png " ")

  e) Notice that two filters are applied. Fewer rows are displayed because only the rows that meet both the filter criteria are disaplyed. You can remove each filter by clicking the Remove Filter icon, next to the filter you want to remove.  
  Click the **Remove Filter** icon next to both the filters

  ![Remove Filters](images/delete-filter1.png " ")

6. Now imagine you want to sort the report on the **Cost** column.   
  a) Select **Actions** > **Data** > **Sort**.

  ![Select Sort](images/select-sort.png " ")

  b) Remove the existing sort columns under **Column** by using the select list in rows 2 and 3 of the Column column to restore the value to the default **- Select Column -**.

  ![Create Sort for ASC](images/create-sort1.png " ")

  c) Select **Cost** for Column, **Descending** for **Direction** and click **Apply**.

  ![Create Sort for DESC](images/create-sort2.png " ")

  d) The report is now sorted in the **Descending** order of **Cost**.

7. Create an aggregation against the **Available Budget** column. You want to display the sum of the **Available Budget**.  
  a) Select **Actions** > **Data** > **Aggregate**.

  ![Click Aggregate](images/select-aggregate.png " ")

  b) In the **Aggregate** dialog, select **Sum** for Function, **Available Budget** for Column. Click **Apply** to add the aggregation at the end of the last column of the report

  ![Create Aggregate](images/create-aggregate1.png " ")

  c) The aggregate function is applied on the column. Notice that the sum of **Available Budget** is displayed at the end of the report under the column. Navigate till the last page to view the sum.

  ![Run Interactive Report3](images/run-ir3.png " ")

8. In the report, suppose you want to include **Cost** calculated with tax. The computation you want to make is **Cost * 1.05**. You create a computed column in the interactive report.

  a) Select **Actions** > **Data** > **Compute**.

  ![Select Compute](images/select-compute1.png " ")

  b) The Compute dialog appears.  
  For Column Label, enter **Cost with Tax**.  
  For Computation Expression, click **Cost** under Columns. Click *1.05 under Keypad.  
  Click **Apply**.

  ![Create Compute](images/create-compute1.png " ")

  c) The new computed column **Cost with Tax** now appears in the report.

  ![Run Application4](images/run-ir5.png " ")

9. Create a Control Break on the **Project** column.  
    a) Select **Actions** > **Format** > **Control Break**.

    ![Select Control Break](images/create-control-break.png " ")

    b) In the Control Break dialog, in row number 1, select **Project** for Column, and click **Apply**.

    ![Create Control Break](images/create-cb1.png " ")  

    c) The control break is now applied. Notice that the aggregation that you created in a previous step appears at the end of each control break.

    ![Run Application5](images/run-ir6.png " ")  

10. Let's say, you want to highlight those rows with **Cost** value less than or equal to **500**. You add the highlighting to rows while continuing with the control break that you created in the previous step.  
  a) Select **Actions** > **Format** > **Highlight**.

   ![Select Highlight](images/select-highlight.png " ")

  b) In the Highlight dialog, enter **Cost less than or equals 500** for Name.  
  Select **Green** for Background Color and **Black** for Text Color.  
  For Highlight Condition: Select **Cost** column, and **<=** Operator. Enter  **500** for Expression.  
  Click **Apply**.

   ![Create Highlight](images/create-highlight1.png " ")  

  c) Notice that the rows that meet the condition are highlighted in Green color.

   ![Run Application6](images/run-ir7.png " ")    


11. Now, You want to control the number of rows to display in your **Interactive Report** page.

  a) Select **Actions** > **Format** > **Rows Per Page** > **50**.

   ![Select Rows Per Page](images/select-rpp.png " ")

  b) Notice that the **Rows Per Page** in your Interactive Report is now **1-50**.

   ![Rows Per Page](images/run-ir8.png " ")


12. In your interactive report, you want to include a Chart to display the Average **Cost** for each **Project**. Your interactive report should include both the Report and Chart views to toggle.

  a) Select **Actions** > **Chart**.

  ![Select Chart](images/select-chart1.png " ")

  b) In the Chart dialog, select / enter the following:  

      • Chart Type: **Bar**  
      • Label: **Project**  
      • Value: **Cost**  
      • Function: **Average**  

      Click **Apply**.

   ![Create Chart](images/create-chart1.png " ")

  c) The chart is created. Toggle between the View Chart and View Report.

   ![View Chart](images/run-ir9.png " ")

13. Create a Group By report to display each **Project** with the **Total Budget**.  
  a) Click View Report.  
  Select **Actions** > **Group By**.

   ![Select Group By](images/select-groupby.png " ")    

  b) In the Group By dialog enter / select the following:  
    • Group By Column: **Project**  
    • Function: **Sum**  
    • Column: **Budget**  
    • Label: **Total Budget**  
    • Format Mask: Select **$5,324.10** from the Format Mask list of example formats.
    Make sure you enable Sum and click **Apply**.

   ![Create Group By](images/create-groupby.png " ")   

  c)  The Group By report is created. You also see the sum of the Budget. Notice that the icon for View Group By is also added.

   ![View Group By](images/run-ir10.png " ")

  d) Click the **X** to the right of **Edit Group By** to remove the filter.

   ![Edit Group By](images/run-ir11.png " ")

14. You want to display the **Sum** of Cost that are available with each **Project** and **Assigned To**. The results should be in a crosstab format. Create a Pivot Report.  
  a) Click **Actions** > **Pivot**.

   ![Select Pivot](images/select-pivot.png " ")

  b)  In the Pivot dialog enter / select:  
   - Pivot Columns: **Assigned To**
   - Row Columns: **Project**
   - Functions: **Sum**
   - Column: **Cost** and **Budget**
   - Label: **Total Cost** and **Total Budget**
   - Set **Sum** to **Yes**.
    Click **Apply**.

   ![Create Pivot](images/create-pivot1.png " ")

  c) The Pivot report is displayed, and a View Pivot icon is created next to Actions button.

  ![View Pivot](images/run-ir12.png " ")

15. You want to save the report with all the customization.  
    a) Select **Actions** > **Report** > **Save Report**.

     ![Select Save Report](images/save-report.png " ")

    b) Enter **My Private Report** for Name and click **Apply**.

     ![Enter Name for Report](images/save-report1.png " ")

16. A drop-down list automatically appears with the report you just created being selected. You can view the default primary report.
You want to reset the **Primary Report** back to the default settings and remove any customizations that you have made so far.  

  a) Select **Primary Report** from the Reports drop down list. The primary report is now displayed. You can make any changes to this report and it will not be reflected in the 'My Private Report' private report you just created.

  ![Navigate to Primary Report](images/nav-primary-report.png " ")

  b)  To restore the primary report back to its default settings, Select **Actions** > **Report** > **Reset**.

  ![Select Reset](images/reset-report.png " ")

  c) In the Reset dialog, click **Apply**.

  ![Click Apply](images/apply-reset.png " ")

  d) From the Reports drop down list, select **My Private Report**.

  ![Select My Private Report](images/nav-to-priv.png " ")

17. You want to download the customized report as a CSV.  
  a)  Select **Actions** > **Download**.

  ![Select Download](images/download1.png " ")

  b)  In the Download dialog, select **CSV**.

  ![Select CSV](images/download2.png " ")  

  c) The report is now downloaded as a CSV.

  ![CSV Downloaded](images/download3.png " ")   


## Task 2: Customizing an Interactive report as a Developer

In this lab, you edit an interactive report in page designer and customize it for end users.
1. First, view the Interactive Report in page designer. In the Developer Toolbar,
click **Edit Page \<n\>**.

 ![Edit Page](images/click-page1.png " ")  

2. When the end users click an edit icon for a specified row, they should be directed to a page which shows the column values for that row. The interactive report currently has a link column to a Form Page. Modify your interactive report to have a link to single row view.
<!-- In the Developer Toolbar, click Edit Page <n>.  -->
  a) Under Rendering, navigate to **Projects** Interactive Report and then on the Property Editor select **Attributes**. Under **Link**, for **Link Column**, select **Link to Single Row View**. Click **Save and Run Page**.

  ![Add Link Attribute](images/change-srw.png " ")

  b)  In the report, ensure that you've selected the "1. Primary Report" the report toolbar. click the **edit icon** (**pencil**) for any row.

  ![View Report with link](images/view-srw1.png " ")

  c) The single row view is displayed. Click **Report View** button to return to the report.
   ![Report View](images/view-srw2.png " ")

3. The current pagination type of the interactive report is **Row Ranges X to Y**. Suppose you want to always show your end users the total number of rows in the report as part of the pagination display. In the Developer Toolbar, click **Edit Page \<n\>**.  

  a) Under Rendering, navigate to **Projects** Interactive Report and select **Attributes** in the **Property Editor**.  

  b) In the **Property Editor**, Under **Attributes**, Search for **Pagination**. For Type, **select Row Ranges X to Y of Z**.

  ![Change Pagination](images/change-pagination.png " ")

4. You want to customize the display of the Search Bar. End users should be able to select the display of desired number of rows per page.  
In the property editor, locate **Search Bar** under **Attributes**. Perform the following:
  - Enable Rows Per Page Selector.
  - Enter **10** for **Maximum Rows Per Page**.

  ![Select Rows Per Page Selector under Attributes](images/enable-rpp.png " ")

  ![Define Maximum rows per page](images/enable-rpp1.png " ")

5. You want to disable the Email in the Download option of the Actions menu. In the property editor, navigate to Download. Deselect **Send as Email** download format.

  ![Deselect Send as email](images/disable-email1.png " ")

6. You want to enable the **Excel** and **PDF** formats in the Download option of the **Actions** menu. In the property editor, navigate to Download. Select **Excel** and **PDF** download formats.

  ![Select Excel and PDF](images/enable-downloads2.png " ")

7. Now that you finished the customization for end users, click **Save** and **Run Page**.

8. Notice that the **row selector** and the **New pagination type** are available on the report.

  ![View Report with new pagination type](images/run-ir13.png " ")

9. Select **Actions** > **Report** > **Save Report**.

  ![Select Save Report](images/save-report2.png " ")

10. The Save Report dialog displays. Notice that the **Public** check box is now available. Perform the following:
 - For Save, select **As Named Report**
 - For **Name**, enter **Projects Public Report**
 - Enable the **Public** checkbox

  Click **Apply**.

  ![Define Name](images/save-report4.png " ")

11. This report is now saved as a public report for all users and is available in the Reports drop down list.

  ![View Public IR](images/view-public-report.png " ")

12. Click **Actions** > **Download**.

13. Notice that the **Excel** and **PDF** formats are available. Click **Close** icon.

  ![Select Download2](images/view-download1.png " ")

  ![Notice Excel and PDF](images/save-report5.png " ")

14. From the Reports drop down list, select **Primary Report**.

## **Acknowledgments**

- **Author** - Roopesh Thokala, Product Manager
- **Last Updated By/Date** - Roopesh Thokala, Product Manager, May 2021
