---
lab:
    title: 'Lab 0 - Setup and environment preparation'
    module: 'Module 0 - Setup'
---

# Setup the lab environment

**⏱️ The estimated time to complete this lab is 30 minutes.**

Attention to MCTs: Please make sure you are familiar with
the TrainerPrepGuide for this course, especially the teaching tips and
recommendations. 

## WWL Tenants - Terms of Use
If you are being provided with a tenant as a part of an instructor-led training delivery, please note that the tenant is made available for the purpose of supporting the hands-on labs in the instructor-led training.
Tenants should not be shared or used for purposes outside of hands-on labs. The tenant used in this course is a trial tenant and cannot be used or accessed after the class is over and are not eligible for extension.
Tenants must not be converted to a paid subscription. Tenants obtained as a part of this course remain the property of Microsoft Corporation and we reserve the right to obtain access and repossess at any time. 

## Introduction

Let's get started. In this first lab, you will acquire a Power Platform 
trial tenant and access the Power Platform admin center. In the admin 
center, you will create the environments for use during the course.

You will also see the Power Automate Desktop application and install .NET 
and Browser extension pre-requisities which are required for the remainder 
of the course. 


## Exercise 1 - Acquire your Power Platform trial tenant

In this exercise, you will add a Power Apps trial to the tenant and assign licenses to users.

### Task 1.1 – Acquire your Power Platform trial tenant

1.  Verify that you have your **Microsoft 365 credentials** from the Authorized Lab Host available. 

2.  In a new browser tab, navigate to `https://powerapps.microsoft.com` and select **Start free**. 

3.  Enter the `email address` provided by the Authorized Lab Host. 

4.  Select **Sign in**. 

5.  Enter the `password` provided by the Authorized Lab Host. 

6.  Select **Yes** to stay signed in. 

7.  The Power Apps maker portal will load in a new tab. 


### Task 1.2 – Verify your Power Apps license has been assigned

1.  In a new browser tab, navigate to `https://admin.microsoft.com`

1.  In the left-hand navigation, expand **Users** and select **Active users**.

1.  Select your user **MOD Administrator** to open the user details panel and select the **Licenses and apps** tab. ![Mod Administrator licenses.](../L00/media/mod-administrator.png)

1.  Verify an appropriate **Power Apps** license is selected. If not, retry Task 1.1.

    > **Note:** Find out more about Power Apps licensing on [Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/admin/signup-for-powerapps-admin).

1.  Select the **X** in the top right of the pane to close the panel. 


### Task 1.3 – Assign Power Apps licenses to other users

1.  In the left-hand navigation, expand **Users** and select **Active users**.

1.  Check the boxes next to the other users, select the **ellipses (...**) menu in the action bar, and select **Manage product licenses**.

    ![Select other users.](../L00/media/select-users.png)

1.  Select **Assign more** and select an appropriate **Power Apps** license.

    > **Note:** Find out more about Power Apps licensing on [Microsoft Learn](https://learn.microsoft.com/en-us/power-platform/admin/signup-for-powerapps-admin).

    ![Add more licenses.](../L00/media/add-licenses.png)

1.  Select **Save changes**.

1.  Select **Done**.


## Exercise 2 - Create your environments

In this exercise, you will create your Development and Test environments
that you will do the majority of your lab work in. 

### Task 1 – Create Development environment

A developer environment might already exist in your Microsoft tenant, if not:

1.  Open a new tab, navigate to `https://powerapps.microsoft.com/en-us/developerplan` and
    select **Existing user? Add a dev environment**, log in with your Microsoft
    365 credentials if prompted again. 
    
2.  Select **Accept**. 

3.  Your **Dev** environment should now show in the list of
    Environments. This typically is named **MOD Administrator’s
    Environment**. For the rest of this course when it says Dev
    environment it will be referring to this environment. 

    > Note: It might take a couple of minutes for the new environment to be provisioned and become available in the list of the environments. You can see the progress of the environment creation in the [Power Platform admin center](https://admin.powerplatform.microsoft.com). You can proceed with the rest of this lab while the environment is provisioned, it must be finished before you start the next lab. 


### Task 2 – Create a Test environment 

1.  Open a new tab, navigate to `https://aka.ms/ppac` and log in with your Microsoft 365 credentials if prompted again and select **Get Started**.

2.  Select **Environments** and select **+ New** from the command bar. 

3.  For **Name**, enter **\[my initials\] Test** (Example: AJ Test) 

4.  For **Type**, select **Trial**. 

5.  Change the toggle on **Add a Dataverse data store?** to **Yes**. 

6.  Leave all other selections as default and select **Next**. 

7.  On the **Add Dataverse** tab, using the **+ Select** button under **Security group**, select **None** and then select **Done**.

8.  Select **Save**. 

9.  The **Test** environment should now show in the list of Environments. 

    > **Note:** The environment may take a few minutes to provision. Refresh the **Environments** list if needed. When your environment shows as 'Ready', select the **Test** environment by selecting the ellipses menu and selecting **Settings**. 

10. Explore the different areas available in **Settings** but do not make any changes yet. 


## Exercise 3 - Power Automate Software 

In this excercise, you will be configuring Power Automate Desktop and accompanying applications.


### Task 1 - Configure Power Automate Desktop 

Power Automate Desktop is installed by default on Windows 11, but you will need to sign in and configure the environment. 

1.  Search the **Start** menu for `Power Automate` and open the **Power Automate** app. 

2.  When Power Automate Desktop opens, sign in using your Office 365 Tenant credentials. Select **Next** and **Get started**. 

    > Optional: Select **Start tour** and go through the welcome prompts to get a feel for the application. 

3.  From the **Environments** list, select your **Dev** environment. 


### Task 2 - Configure the Power Automate Machine-Runtime App 

To run attended and unattended flows across cloud and desktop environments, the **machine-runtime app** needs to be configured. 

1.  In Power Automate Desktop, select **⚙️ Settings**. Under Machine settings, select **Open machine settings**. 

2.  On the **Machine settings** screen, select your **Dev** environment. The machine-runtime app will register the machine in the Dev environment's Dataverse database. You should see a success notification "Your machine XXXXYYX has been registered". 

    **Note:** If you get an error stating a premium license is required, in the message select the Get Premium option and start a trial.

3.  Once it's connected, you can close the **Power Automate machine runtime** window.  


## Exercise 4 - Azure account setup

In this exercise, you will create your Azure account that you will be
using in the labs.

1.  Get a new Azure Pass (valid for 30-days) from the instructor or
    other source.

2.  Use a private browser session, go to Microsoftazurepass.com to
    redeem your Azure Pass using the Microsoft 365 credentials provided
    to you). [Redeem a Microsoft Azure
    Pass](https://www.microsoftazurepass.com/Home/HowTo?Length=5) Follow
    the instructions for redemption.

After the account setup completes, setup the following Virtual Machine.

3.  Navigate to `https://portal.azure.com`

4.  Select **+ Create a resource**.

5.  Select **Create** Virtual Machine. 

    <img src="../L00/media/image1.png" style="width:5.17644in;height:1.88518in"
    alt="Screenshot showing Virtual Machine Azure resource with red rectangle around the create button" />

6.  Select **Create new resource** group. 

    <img src="../L00/media/image2.png" style="width:6.5in;height:1.61667in"
    alt="Screenshot showing the create resource dialog with a red rectangle around the create resource group button" />

7.  Enter `Funding` for **Name** and select **OK**. 

8.  Enter `Funding` for virtual machine name.

9.  Select **Windows 11** Image.

10. Enter `Funding` for Username.

11. Create a secure password and make a note of it.

12. Confirm the Password. 

13. Check the box for *I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights.* under **Licensing**.

14. Select **Review + create**. 

    <img src="../L00/media/image3.png" style="width:5.04419in;height:4.23637in"
    alt="Screenshot showing the create new virtual machine resource dialog" />

15. Select **Create**. 


## Exercise 5 – Copy Lab Resources

1.  Create a folder **Labs** on the **C:** drive if you don't already have that folder.

2.  Copy the lab resources folder to **C:\Labs** if it doesn't already exist.

3.  Browse to **C:\Labs\Resources\Funding manager app** and double-click
    on the **Woodgrove Bank Funding Manager.exe** file.

4.  Select **Yes** on the download .NET popup.

    <img src="../L00/media/image5.png" alt="Screenshot showing the download .NET dialog" />

5.  Select open file on the downloaded .exe file in the browser downloaded file list. 

6.  Select **Install** and wait for the installation to complete.

    <img src="../L00/media/image7.png" alt="Screenshot showing the .NET Windows desktop runtime installation wizard" />

7.  Select **Close** after the installation completed.

8.  Browse to **C:\Labs\Resources\Funding manager app** and double-click
    on the **Woodgrove Bank Funding Manager.exe** file again. 

    <img src="../L00/media/image8.png" alt="Screenshot showing the Woodgrove Bank Funding Manager.exe file" />

9.  The app should launch. **Close** the application. 


