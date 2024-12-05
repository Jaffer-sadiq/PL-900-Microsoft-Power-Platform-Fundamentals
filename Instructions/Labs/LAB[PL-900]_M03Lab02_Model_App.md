# Lab 3: How to build a model-driven app

## Lab scenario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Campus administration would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Throughout this course, you will build applications and perform automation to enable the Bellows College administration and security personnel to manage and control access to the buildings on campus.

In this lab, you will build a Power Apps model-driven app to allow the backoffice campus staff to manage visit records across the entire campus.

## Lab objectives
In this lab, you will perform:
+ Exercise 1: Customize Views and Forms
+ Exercise 2: Create Model-driven app

## Estimated time: 40 minutes

## High-level lab steps

As part of creating the model-driven app, you will complete the following:

- Create a new model-driven app named Bellows Campus Management

- Edit the app navigation to reference the required tables

- Customize the forms and views of the required tables for the app

We will work with the following components:

- **Views**: Views allow the user to display the existing data in the form table.

- **Forms**: This is where the user creates/updates new rows in the tables.

Both will be integrated to the model-driven app for a better user-experience.

## Prerequisites

- Completion of **Lab 0 - Validate lab environment**
- Completion of **Lab 1 - Data Modeling**

## Things to consider before you begin

- What changes should we make to improve the user experience?
- What should we include in a model-driven app based on the data model we have built?
- What customizations can be made on the sitemap of a model-driven app?

## Exercise 1: Customize Views and Forms

**Objective:** In this exercise, you will customize views and forms of the custom created tables that will be used in the model-driven app.

### Task 1: Edit Visit Form

1. Sign in to [https://make.powerapps.com](https://make.powerapps.com/) if you are not already signed in.

2. Select your **Practice<inject key="DeploymentID" enableCopy="false"/>** environment at the top right if it is not already selected.

3. Using the navigation on the left, select **Tables**, and click to open your **Visit** table.

   >Note: If you do not see the Visit table, make sure you are in the correct environment (Step 2).

4. Under the **Data experiences** section, select **Forms** and click to open the Information form with **Main** form type.

   **IMPORTANT:** Since by default all forms are named Information, make sure to verify that the form you select has a Form Type of **Main** and not something else. By default, the form has two fields: Name and Owner.

   ![](media/lab3-1n.png)

   ![](media/lab3-2n.png)

5. On the right side of the screen on the Properties panel, select the **Display Name** field, and change it to **Main Information**.

6. Select the **Table Columns** from the left navigation pane and add the following fields below the **Owner** field by dragging columns to the form or simply clicking column names:

	1. **Visitor (1)**

	1. **Scheduled Start (2)**

	1. **Scheduled End (3)**

	1. **Actual Start (4)**

	1. **Actual End (5)**

7. Drag the **Code (6)** column and drop it in the form header.

	The header is the top right area of the form. You may need to collapse the Properties panel on the right side of the screen to see the field on the form.

   ![](media/pl900lab3n.png)

8. With the **Code** field still selected, check the checkbox for **Read-only** in the Properties panel on the right side of the screen.

   ![](media/lab3-4n.png)

9. Select **Owner** field. In the Properties panel, change the **Label** to **Host**

   ![](media/lab3-5n.png)

10. Select the **Save and publish** at the top right and wait for for the publishing to complete.

11. If the edit view opened in a new browser tab or window, close it. Otherwise, click **Back** at the top left of the screen. You should now be back to the Visit tables Forms.

12. Using the breadcrumbs in the upper left (Tables>Visit>Forms). Select **Visit** to return to the **Visit** table main screen.

### Task 2: Edit Active Visits view

In this task, we will modify the default Active Visits view and create a new view for today’s visits.

1. Under the **Data experiences** section, select **Views** and click to open your **Active Visits** view.

2. Add the following fields to the view by either clicking or dragging and dropping the fields:

	1. **Code**

	2. **Visitor**

	3. **Scheduled Start**

	4. **Scheduled End**

3. Click the **Created On** column and select **Remove**. Field **Created On** will now be removed from the view.

4. Resize the individual column widths to fit the data.

5. Select **Scheduled Start** to change the sort order to **Newer to Older**.

6. Select the **Save and publish** and wait for the publishing to complete.

### Task 3: Create new view for today’s visits

Now, we will clone the view to create a new view for today’s visits.

**IMPORTANT**: Make sure that you do not close the Active Visits view, as we will be leveraging it to create the new today’s visits view.

1. Click on the **Save As** button.

2. Change the **Name** to `Today’s Visits` and select **Save**.

3. Select **Edit filters** link in the Properties panel.

4. Select **+ Add**, select **Add row**.

5. Select **Scheduled Start** as a field, then select **Today** as the condition in the drop-down.

6. Select the **…** on the **Status** row and click **Delete** to delete that filter condition.

7. Select **Ok** to save the condition. The view is now filtered to show only records where the Scheduled Start date is today.

8. Add **Actual Start** and **Actual End** fields to the view.

   >**Note:** Since we no longer filter on the view status, we will get all today’s visits including completed ones. These fields will help to differentiate completed visits and visits in progress.

9. Select the **Save and Publish** and wait for the publishing to complete.

## Exercise 2: Create Model-driven app

**Objective:** In this exercise, you will create a model-driven app, customize the sitemap, and test the app.

For simplicity and time’s sake, we will not be addressing some of the Visit columns in this lab.

### Task 1: Create app

1. Sign into [https://make.powerapps.com](https://make.powerapps.com/) (if you are not already signed in).

2. Select your **Practice<inject key="DeploymentID" enableCopy="false"/>** environment at the top right if it is not already selected.

3. Select **+ Create** on the left navigation.

4.  Create the Model-Driven Application:

    1. Select **Blank app** in the **Start from** section of the **Create your app** screen.

    2. Under **Blank app based on Dataverse**, select **Create**.

    3. Enter `Bellows Campus Management` for **Name** and select **Create**.

5. After your new model-driven application loads, select the **+ Add Page** button.

6. On the Add Page screen, choose **Dataverse table**.

7. Add the following tables:

	1. Visit

	1. Contact

8. After you have selected the 2 tables, select **Add**.

9.  Using the navigation icons on the left side of the screen, select **Navigation**.

10. On the Navigation Pane, select **New Group** below where it says Navigation. You may need to expand the menu on the left.

11. On the right side of the screen, in the **Display options** section, change the **Title** property to `Security`

12. Select **Save** and wait until the changes are saved.

13. Once the **Save** is complete, select the **Publish** button to publish your changes. 

### Task 2: Test app

1. Start the application

	1. Select the **Play** button, the new app will load in a new tab.

2. Create new Contact

	1. The app should open to the **My Active Contacts** view. If it does not, select Contacts on the left-hand navigation.

	1. Click **+ New** from the top menu.

	1. Provide **First Name** as John and **Last Name** as Doe.

	1. Provide your **personal email** as **Email**. This will be used in a future lab where you will receive an email.

	1. Click **Save & Close**.

	1. You should now see the created contact on the **My Active Contacts** view.

3. Create new Visit

	1. Select **Visits** from the left-hand navigation of the sitemap.

	1. Click **+ New**.

	1. Enter the fields as following

		1. **Name**: New test visit

		1. **Visitor**: select John Doe

		1. **Scheduled Start**: select tomorrow’s date and 2:00 PM as start time

		1. **Scheduled End**: select tomorrow’s date and 3:30 PM as end time

1. Click **Save & Close**. This will create the Visit and you should be able to see it on the Active Visits View.

1. Change view to **Today’s Visits** by using the drop down next to **Active Visits**. You should no longer see the new visit in the view, since it is scheduled for tomorrow.

4. You may add more test records.

   Your running app should look approximately like the following:

   ![](media/PL-900_lab03_e2_t2_s4.png)

You have created and configured your first model-driven app.

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
      
   - If you receive a success message, you can proceed to the next task.
   - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="cc68b724-6189-4c55-8c93-0de56b3c08d2" />

## Challenges

- Select specific views and forms for Contacts.

### Review
In this lab, you have completed:
- Customize Views and Forms
- Create Model-driven app

### Proceed with the next Lab.
