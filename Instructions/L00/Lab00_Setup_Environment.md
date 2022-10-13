# Setup my lab environment

Attention to MCTs: Please make sure you are familiar with
the TrainerPrepGuide for this course, especially the teaching tips and
recommendations.

## Scenario

In this Module 0 lab, you will acquire a Power Platform trial tenant,
access the Power Platform admin center. In the admin center, we will
create individual environments for configuration during the course.

## Exercise 1 - Acquire your Power Platform trial tenant

-   Copy your **Microsoft 365 credentials** from the Authorized Lab
    Hoster.

-   Navigate to <https://powerapps.microsoft.com> and click **Start free.**

-   Enter the email address from your Microsoft 365 credentials.

-   You see a prompt that you have an existing account with Microsoft.
    Select **Sign in.**

-   Enter the password provided by the Authorized Lab Hoster.

-   Select **Yes** to stay signed in and complete the sign up process by clicking **Get Started**.

## Exercise 2 - Create your environments

In this exercise, you will create your Development and Test environments
that you will do the majority of your lab work in.

### Task 1 – Create Development environment

1.  Access <https://powerapps.microsoft.com/en-us/developerplan> and
    select *Existing user? Add a dev environment*, log in with your Microsoft
    365 credentials if prompted again.

2.  Your **Dev** environment should now show in the list of
    Environments. This typically is named **MOD Administrator’s
    Environment**. For the rest of this course when it says Dev
    environment it will be this environment.
> Note: It might take a couple of minutes for the new environment to be provisioned and become available in the list of the environments. You can see the progress of the environment creation in the [Power Platform admin center](https://admin.powerplatform.com). You can proceed with the rest of this lab while the environment is provisioned, it must be finished before you start the next lab.


### Task 2 – Create Test environment

1.  Access [https://admin.Powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com/) and
    log in with your Microsoft 365 credentials if prompted again.

2.  Select **Environments** and click **+ New**.

3.  For **Name**, enter **\[my initials\] Test** (Example: AJ Test)

4.  For **Type**, select **Trial**.

5.  Change the toggle on **Create a database for this
    environment?** to **Yes**.

6.  Leave all other selections as default and click **Next**.

7.  On the next tab, leave all selections to default and click **Save**

8.  Your **Test** environment should now show in the list of
    Environments.

9.  Your environment may take a few minutes to provision. Refresh the
    page if needed. When your environment is prepared, select
    your **Test** environment by clicking on the ellipses next to its
    name to expand the drop-down menu and select **Settings.**

10. Explore the different areas in **Settings** that you are interested
    in but do not make any changes yet.

## Exercise 3 - Install Power Automate on your device

1.  Follow the instructions to install Power Automate -
    <https://go.microsoft.com/fwlink/?linkid=2102613>. Open downloaded file to start install.

2.  Check Install the Power Automate for desktop to build desktop flows
    (if unchecked) and take the default options for the rest. Check "By selecting 'Install', you agree to Microsoft's terms of use". If you
    receive a warning about a duplicate install, go ahead and accept the
    install. Note: If you are completing the labs in an environment
    OTHER than through a hosted learning environment, check with your
    admin to determine the best course of action for this step.

3.  Launch the app and login with your Microsoft 365 credentials

4.  From the environment list pick your Dev environment

5.  Click Go Premium to start a trial and follow the prompts to activate
    the trial.

## Exercise 4 - Azure account setup

In this exercise, you will create your Azure account that you will be
using in the labs

1.  Get a new Azure Pass (valid for 30-days) from the instructor or
    other source.

2.  Use a private browser session, go to Microsoftazurepass.com to
    redeem your Azure Pass using the Microsoft 365 credentials provided
    to you). [Redeem a Microsoft Azure
    Pass](https://www.microsoftazurepass.com/Home/HowTo?Length=5) Follow
    the instructions for redemption.

After the account setup completes, setup the following Virtual Machine.

3.  Navigate to <https://portal.azure.com>. Click + Create a resource.

4.  Click **Create** Virtual Machine.

<img src="../L00/media/image1.png" style="width:5.17644in;height:1.88518in"
alt="Screenshot showing Virtual Machine Azure resource with red rectangle around the create button" />

5.  Click Create new resource group.

<img src="../L00/media/image2.png" style="width:6.5in;height:1.61667in"
alt="Screenshot showing the create resource dialog with a red rectangle around the create resource group button" />

6.  Enter **Funding** for Name and click **OK**.

7.  Enter **Funding** for virtual machine name

8.  Select **Windows 11** Image.

9.  Enter **Funding** for Username

10. Enter **relecloud@word1** for Password

11. Confirm Password.

12. Place check in box for *I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights.* under *Licensing*.

13. Click **Review and create**.

<img src="../L00/media/image3.png" style="width:5.04419in;height:4.23637in"
alt="Screenshot showing the create new virtual machine resource dialog" />

14. Click **Create**

## Exercise 5 – Copy Lab Resources

1.  Create a folder name Labs in the **C:** if you don't already have that folder.

2.  Copy the lab resources folder to **C:\Labs** if it doesn't already exist.

3.  Browse to **C:\Labs\Resources\Funding manager app** and double click
    on the **Woodgrove Bank Funding Manager.exe** file.

4. Click **Yes** on the download .NET popup.

<img src="../L00/media/image5.png" alt="Screenshot showing the download .NET dialog" />

5. Select open file on the downloaded .exe file in the browser downloaded file list.

6. Click **Install** and wait for the installation to complete.

<img src="../L00/media/image7.png" alt="Screenshot showing the .NET Windows desktop runtime installation wizard" />

7. Click **Close** after the installation completed.

8. Browse to **C:\Labs\Resources\Funding manager app** and double click
    on the **Woodgrove Bank Funding Manager.exe** file again.

<img src="../L00/media/image8.png" alt="Screenshot showing the Woodgrove Bank Funding Manager.exe file" />

9.  The app should launch. Close the application.
