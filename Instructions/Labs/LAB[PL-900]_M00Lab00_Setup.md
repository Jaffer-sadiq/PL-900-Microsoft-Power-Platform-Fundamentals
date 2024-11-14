# Lab 0: Validate lab environment

## Scenario

Bellows College is an educational organization with multiple campuses and programs. Many of Bellow Colleges instructors and administrators need to attend events, and purchase items. Historically tracking these expenses has been a challenge.

Campus administration would like to modernize their expense reporting system where employees submit expenses.

Throughout this course, you will build applications and perform automation to enable Bellows College employees to manage expenses.

In this Module-lab 0, you will acquire a Power Platform trial and access the Power Platform admin center. In the admin center, you will then create a **Dev One** environment that will be used for majority of the lab executions.

## Exercise 1: Setup

### Task 1: Acquire your Microsoft Power Platform trial tenant

1. Signup to Powerapps using Powerapps Trial link provided below

   ```
   https://apps.powerapps.com/trial
   ```

1. You'll see the **Sign in** tab. Here, enter your credentials:
 
   - **Email/Username:** <inject key="AzureAdUserEmail"></inject>
 
     ![Enter Your Username](../Media/sc900-image-1.png)
 
1. Next, provide your password:
 
   - **Password:** <inject key="AzureAdUserPassword"></inject>
 
      ![Enter Your Password](../Media/sc900-image-2.png)

1. If **Action required** pop-up window appears, click on **Ask later**.

   ![Ask Later](../Media/2test1.png)
    
1. Select **Yes** to stay signed in.

1. On the **You need a Power Apps license to use this app** page, select **Start a 30-day trial**
   
    ![Ask Later](../Media/lab0-1.png)

1. Select **Start my trial**

    ![Ask Later](../Media/lab0-2.png)

### Task 2: Create environment

1. Navigate to Powerplatform admin center using the below URL and log in with the credentials provided before if prompted.

  ```
  https://admin.powerplatform.microsoft.com
  ```

1. If you see a Welcome popup, click **Get Started**.

1. Select **Environments** and click **+ New**.

    1. For **Name**, enter **Dev One**

    1. For **Type**, select **Trial** (Do not select the Trial
        (subscription-based) option).

    1. Change the toggle on **Add a Dataverse data store?** to **Yes**.

    1. Leave all other selections as default and click **Next**.
  
    1. Click the **+ Select** button under the **Security group** heading.
   
    1. Select the **None** item under the **Open access** heading and then select **Done**..

    1. Leave the remaining options at their defaults and select **Save**.

1. Your **Dev One** environment should now show in the list of Environments.

   > **Note**: Your environment may take a few minutes to provision. Refresh the page if needed.

## Proceed to next lab
