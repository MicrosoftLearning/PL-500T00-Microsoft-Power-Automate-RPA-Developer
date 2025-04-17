---
lab:
    title: 'Lab 2 - Build Desktop Flows'
    module: 'Module 2 - Desktop Flows'
---

# Building Desktop Flows

## Scenario

In this lab, you will be creating two desktop flows. One to automate the funding
Windows app and the other to automate the inspection website.

## High-level lab objectives

-   Use recording to capture steps to automate for both web and Windows desktop
    applications

-   Use input and output variables

-   Use flow control to handle conditional logic

-   Use loop condition and wait control

-   Use JavaScript to build JSON

## Exercise 1: Automate Desktop Funding Application

### Task 1: Practice using app

In preparation for recording practice using the app to help eliminate accidental
steps from being recorded.

1.  Browse to **C:\\Labs\\Resources\\Funding manager app** and launch the
    **Woodgrove Bank Funding Manager.exe** app.

    ![Screenshot showing the Woodgrove Bank Funding Manager.exe
    file](media/6b775655e69ec67e1cdbcd4645cb2967.png)

1.  Enter **your username** for Username, `pass@word1` as Password, and click
    **Login**.

1.  Enter `MC3747` for Loan number and click **Lookup**.

1.  Click **Draw Funds**.

1.  Enter `100000` for Amount, `123` for Inspection Job #, `30` for Risk
    Score, check the Borrower Approved Draw checkbox, and click **Draw Funds**.

    ![enter details as described](media/e5316c6d25c4b8aaba0c2710ef7b1dc3.png)

1.  Click **OK**.

1.  Repeat steps **3** to **6** until you feel comfortable with application.

1.  Close the application.

### Task 2: Record using the app

Create a new desktop flow in the **Construction Funding** solution and record
the steps using the **Woodgrove Funding Manager** application.

1.  Navigate to `https://make.powerapps.com/` and make sure you have the Dev
    environment selected.

1.  Select **Solutions** and open the **Construction Funding** solution.

1.  Click **+ New** and select **Automation \| Desktop flow**.

    ![Select +New, Automation - Desktop flow](media/f01b3b585de41552517c81747a4cbb2e.png)

1.  Enter `Woodgrove Funding Manager Draw` for Flow name and click **Launch
    app**.

1.  Power Automate Desktop should launch.

1.  Go to the **Actions** pane, expand the **System** group, and double click on
    the **Run application** action.

    ![select run from the actions available](media/7dbe6eec4e251774813ecfa27d65767f.png)

1.  Click on the **Select file** button of the Application path.

    ![select file](media/Desktopflow_selectfile.png)

1.  Select the **Woodgrove Bank Funding Manager.exe** file located in the lab
    folder **C:\\Labs Resources\\Funding manager app** and click **Open**.

    ![select the exe file](media/988ee9bb1421ff9964da7c37a4624c30.png)

1.  Click **Save**.

1.  Click **Run**.

    ![run the application](media/cd9014812b6db519bd26d9947cc8f50d.png)

1.  The application should start, and the flow should complete.

1.  Do not close the application.

1.  Go to the desktop flow and click **Recorder**.

1.  Do not start recording yet. Close or minimize all but the funding manager
    application. You will be recording steps and modifying steps. Make sure to
    follow the directions here, and only click Finish when we tell you to.

1.  Remember, you will provide the values below once you start recording.

    > Username: **your username**.
    >
    > Password: `pass@word1`
    >
    > Loan number: `MC3747`
    >
    > Amount: `100000`
    >
    > Inspection job #: `123`
    >    
    > Risk score: `30`

    
    **DO NOT** click the **OK** button on the Draw Confirmation screen.

1.  Click **Record** and select **Next**. On Recorder Pane, click on **Record**.

    ![click record](media/30fff4dfe9d7c719d1d316885ee8f15c.png)

1.  The recording should start.

1.  Capture steps, same as you practiced.

1.  **DO NOT** click on the OK button.

1.  On the confirmation screen of the Windows app right click on the **Amount**
    value and select **Get text(“”).**

    ![right click on the item ](media/f5ffffc1dbd901ecaa8ac658da3cb340.png)

1.  Right click on the **Funds transfer number** value and select **Get
    text(“”).**

1.  Right click on the **Funds sequence number** value and select **Get
    text(“”).**

1.  Click **OK**.

1.  Go to the recorder and click **Done**.

1.  The steps you recorded should look like the image below.

    ![summary of steps](media/e559034a4a714a1dac8e1eb629ce1b19.png)

1.  Close the **Woodgrove Funding Manager** application.

1.  If Run Application is no longer your first step, Drag the **Run
    application** action from the bottom to the top of the steps.

    ![reorder to match the description if needed](media/cfa838f9af6f1fb6932a661b90a90094.png)

1.  Click **Run**. Do not interact with your computer until the run completes.

1.  Your flow variables should now look like the image below but might have
    different values.

    ![review flow variables](media/f8ae74206da4886bdeec6cc3f381e39d.png)

1.  Click **Save** and wait for the flow to be saved.

1.  Do not close the desktop flow.

### Task 3: Add Input and output variables

In this task, you will define the input and output variables that you'll use to
replace the hard coded values recorded. The input variables will be used to pass
data from the calling cloud flow. The output variables will be used to return
data to that flow.

1.  On the **Variables** pane, click the plus button **(+)** and select
    **Input** to add a new input variable.

    ![select add ](media/ce0735d304e9a52fe081efbf5875ebcd.png)

1.  Configure the variable as follows:

    > Variable name: `Username`
    >
    > Data  type: Text
    >
    > Default value: **Your Username**
    >
    > External name: `Username`
    >
    > Description: `Username`

    Mark the variable as sensitive, and click **Save**.

    ![enter details as described](media/b031f8dbf29c803b75186c9bd64fb2e9.png)

1.  Click **(+)** and select **Input** again.

    ![add another input](media/c46b834409127cd306a94dfd0deaeced.png)

1.  Enter `Password` for Variable name, select **Text** for Data type,
    `pass@word1` for Default value, `Password` for External name,
    `Password` for Description, mark the variable as sensitive, and click
    **Save**.

1.  Click **(+)** and select **Input** again.

1.  Enter `LoanNumber` for Variable name, select **Text** for Data type, `MC3747` for Default value, `LoanNumber` for External name, `Loan number` for Description, and click **Save**.

1.  Click **(+)** and select **Input** again.

1.  Enter `RequestedAmount` for Variable name, select **Text** for Data type,
    `100000` for Default value, `RequestedAmount` for External name,
    `Requested amount` for Description, and click **Save**.

1.  Click **(+)** and select **Input** again.

1.  Enter `InspectionJobNumber` for Variable name, select **Text** for Data
    type, `123` for Default value, `InspectionJobNumber` for External name,
    `Inspection job number` for Description, and click **Save**.

1.  Click **(+)** and select **Input** again.

1.  Enter `BorrowerApproved` for Variable name, select **Text** for Data type, `Yes` for Default value, `BorrowerApproved` for External name,
    `Borrower approved` for Description, and click **Save**.

1.  Click **(+)** and select **Input** again.

1.  Enter `RiskScore` for Variable name, select **Text** for Data type, `30` for Default value, `RiskScore` for External name, `Risk score` for
    Description, and click **Save**.

1.  You should now have 7 input arguments. They're displayed in alphabetical order.

    ![summary of input variables](media/d2612c2244b649484ce0536d9818b69d.png)

1.  Select **(+)** and select **Output**.

    ![add output variable](media/ab586e011bfa38c2e47dee1e35e17ff2.png)

1.  Enter `FundedAmount` for Variable name, select **Text** for Data type,
    `FundedAmount` for External name, `Funded amount` for Description, and
    click **Save**.

    ![enter details as described](media/4fa1afb6cd8700ac74e63ab7e987e9c5.png)

1.  Click **(+)** and select **Output** again.

1.  Enter `FundTransferNumber` for Variable name, select **Text** for Data
    type, `FundTransferNumber` for External name, `Fund transfer number` for Description, and click **Save**.

1.  Click **(+)** and select **Output** again.

1.  Enter `FundSequenceNumber` for Variable name, select **Text** for Data
    type, `FundSequenceNumber` for External name, `Fund sequence number` for Description, and click **Save**.

1.  Click **(+)** and select **Output** again.

1.  Enter `FundingStatus` for Variable name, select **Text** for Data type, `FundingStatus` for External name, `Funding status` for Description, and click **Save**.

1.  You should now have **11** total variables 7 inputs and 4 outputs.

1.  Click **Save** and wait for the flow to be saved.

### Task 4: Change flow to use input variables

In this task, you will modify hard coded values in the steps to use the input
variables you just defined.

1.  Go to the populate username action and double click on it.

    ![select the item described](media/149e08e4d5803fb1da4c59d985df55a2.png)

1.  Remove the current value and click on the **{x}** select variable button.

    ![click on the variable button as shown](media/72ff19b35b9d3cc9019998d22918998e.png)

1.  Select **Username** for variable and click **Select**.

    ![select user name variable](media/c79c48d2c72a7790ed4fe8ed34889a8e.png)

1.  Click **Save**.

1.  Go to the populate password action and double click on it.

    ![select the item shown](media/6ff77f8b7e0012d53d2fcaadf441b5c2.png)

1.  Click on then encryption button and select **Input as text,** **variable or
    expression**.

    ![enter details as described](media/361bb8619dc64d46a95b4a8521dbdbda.png)

1.  Click on the **{x}** select variable button.

1.  Select **Password** for variable and click **Select**.

1.  Click **Save**.

1.  Go to the populate loan number action and double click on it.

1.  Remove the current value and click on the **{x}** select variable button.

1.  Select **LoanNumber** for variable and click **Select**.

1.  Click **Save**.

1.  Go to the populate amount action and double click on it.

1.  Remove the current value and click on the **{x}** select variable button.

1. Select **RequestedAmount** for variable and click **Select**.

1. Click **Save**.

1. Go to the populate inspection job # action and double click on it.

1. Remove the current value and click on the **{x}** select variable button.

1. Select **InspectionJobNumber** for variable and click **Select**.

1. Click **Save**.

1. Go to the populate risk score action and double click on it.

1. Remove the current value and click on the **{x}** select variable button.

1. Select **RiskScore** for variable and click **Select**.

1. Click **Save**.

1. The actions you changed should now look like the image below.

    ![summary view of work just completed](media/6b9d8384f6480b853e05ac2395fd3362.png)

1.  Click **Save** and wait for the flow to be saved.

### Task 5: Change to populate output variables

In this task, you will modify hard coded values in the steps to use the output
variables you just defined.

1.  In your steps, locate the **Get details of a UI element in window** action
    for the amount and double click on it.

    ![select item described](media/ca8fedce4adecd6db5dfc8cd1f73d2e8.png)

1.  Expand the **Variables produced section** and click on the **{x}** select
    variable button.

    ![select variable button](media/variablesproducedsection.png)

1.  Select **FundedAmount**.

    ![select funded amount](media/3f2fc46af213efe389c3e0b9b8c41f71.png)

1.  Click **Save**.

1.  Locate the **Get details of a UI element in window** action for the transfer
    number and double click on it.

    ![locate the item described](media/2f31137d519d52396abf988d78afbe56.png)

1.  Expand the **Variables produced section** and click on the **{x}** select
    variable button.

1.  Select **FundTransferNumber**.

1.  Click **Save**.

1.  Locate the **Get details of a UI element in window** action for the sequence
    number and double click on it.

    ![select the item described](media/85f10b84237a6da8a89f9b27ef5a0036.png)

1.  Expand the **Variables produced section** and click on the **{x}** select
    variable button.

1.  Select **FundSequenceNumber**.

1.  Click **Save**.

1.  You should now have three output variables populated.

    ![summary of work recently completed](media/f315f7c60a249dfcd878961aec041a48.png)

1.  Click Save and wait for the flow to be saved.

### Task 6: Handle denied draws

In this task, you will handle if the funding is denied by adding conditional
logic to the flow. This will ensure the flow does not have an error when certain
controls are not available, and you will return an output variable indicating
that the funding was denied.

1.  Open the Woodgrove Bank Funding Manager application and go through the steps
    with the following parameters to get the denied message.

    > Username: **your username**.
    >
    > Password: `pass@word1`
    >
    > Loan number: `MC3747`
    >
    > Amount: `100000`
    >
    > Inspection job #: `123`
    >
    > Risk score: `90`

1.  Leave the denied message and don’t click OK.

1.  In Power Automate Desktop, go to the **Actions** pane and expand the **UI
    automation** group.

1.  Drag the **If window contains** action and drop it above the **Get details
    of the UI element in window** of the amount.

    ![drag the action as described](media/fc3963b84575ff22f079046108800f23.png)

1.  Click the UI element dropdown and then click **Add UI element**.

1.  Hold the Ctrl key and Click on the text **Draw denied contact bank**.

1.  Click **Save**.

    ![save the item](media/2d2ef2fb38c1d3f9f14eb1c2294f1d38.png)

1.  Click on the **…** More actions button of the Get details of a UI element in
    window action for the amount.

    ![select more actions](media/bce19d80c975f51c193a53e21aee399b.png)

1.  Select **Copy**.

1.  Right click on the Get details of a UI element in window action for the
    amount and select **Paste**.

    ![complete the copy paste](media/151ccb764aa8a7dbafc40a1750389f79.png)

1.  You should now have two the Get details of a UI element in window action for
    amount.

    ![summary of work just completed](media/261b48c732beb0eb6f8d442028edf678.png)

1.  Drag the first Get details of a UI element in window action for amount and
    drop it inside the **If window** contains.

    ![drag the item as described](media/aaba4a53e575db1306701af4c9707f02.png)

1.  Double click on the Get details of a UI element in window action for amount
    inside the If.

    ![open the item as described](media/5dca0fca65fbf54896ba79788054ec96.png)

1.  Click on the **UI element** dropdown and select **Draw denied contact bank**
    and click **Select**.

    ![from the dropdown select the item as described](media/d994597ac9a41cc97eb3c0d9e522b8b9.png)

1.  Expand the **Variables produced** and click on the **{x}** select variable
    button.

1.  Select **FundingStatus**.

1.  Click **Save**.

1.  Drag another If window contains action and drop it below the **End** if.

    ![drag item as described](media/ff9645a66202ce014b84c62e0cd1f419.png)

1.  Click on the **Check if window** dropdown and select **Doesn’t contain UI
    element**.

1.  Click on the **UI element** dropdown select **Draw denied contact bank** and
    click **Select**.

1.  Click **Save**.

1.  Move all three Get details of a UI element in window actions outside of the
    If and drag them to the inside of the second if condition.

    ![move the items as described](media/7f608fdb00078ea05b13636b77039b71.png)

1.  Expand the **Variables** action group and drag **Set variable** action to
    the second If window contains.

    ![drag the item as described](media/3d46af3755a35348fbc61a47518ee116.png)

1.  Click **{x}** select variable select **FundingStatus**.

    ![select the variable as described](media/9cc31bfb18f04cb7b0d05410808ed532.png)

1.  Type `Approved` for Value and click **Save**.

### Task 7: Add Close of app and Test Run

1.  In the **Actions** pane, search for **close**. Drag **Close window** and
    drop it after the last action.

1.  Select **Windows 'Request Funds Draw'** for Window and then click
    **Select**.

1.  Click **Save** on the Close window step.

1.  Click **Save** and wait for the flow to be saved.

1.  **Close** the funding manager app if it is still running.

1.  Click **Run**. Do not interact with the VM until the run completes.

    ![run the flow](media/0e3de90b544e8ee63c6cfb8c5e91b991.png)

1.  The flow should run successfully. Review the output variables and make sure
    the **FundingStatus** is set to **Approved**.

    ![review the output](media/cfe1ddc3adbf278654dfafe70bbd5db3.png)

1.  Locate the **RiskScore** variable and double click on it.

    ![locate risk score](media/locate_risk_score.png)

1.  Change the **Default value** to **85** and click **Save**.

    ![update the default value](media/bd8487091177055c5c0774edd307c4cc.png)

1.  Click **Run** again. Do not interact with the VM until the run completes.

1.  The flow should run successfully. Review the output variables and make sure
    the **FundingStatus** is set to **Draw denied contact bank**.

    ![review the output](media/9b67744e725e92dd5464df25b87ce352.png)

1.  Locate the **RiskScore** variable and double click on it.

1.  Change the **Default value** to **30** and click **Save**.

1.  Click **Save** and wait for the flow to be saved.

1.  You may close the desktop flow.

## Exercise 2: Automate Inspection web site

### Task 1: Practice using site

In preparation for recording practice using the app to help eliminate accidental
steps from being recorded.
    
 **Note**: Before running this desktop flow from Power Automate Desktop, please ensure to enable **Power Automate Extension** in your Web browser.

1.  Navigate to `https://fabrikaminspectionstest.azurewebsites.net/`

1.  Navigate to the **Request Inspection** page.

1.  Enter your name for Inspection Account\#, enter `123 Main Street` for Property Address, enter `Test work item` for Work to Inspect, and then
    click **Request Inspection**.

    ![enter details as described](media/a8c27884da8c60e0cce79c7297390e5e.png)

1.  Copy the **Job Number** and keep it in your clipboard.

    ![review the output and save it](media/047c43d3df6583acbdcb3d69e8d31de4.png)

1.  Go to the **Inspection Results** page.

1.  Enter your name for Inspection Account \#, paste the Job number you copied,
    and click **Check Inspection**.

    ![enter details as described](media/71c4e231e2123d59a966ee87c1334f5d.png)

1.  The Job Status should show **In progress**.

    ![review the output](media/2377355b6187a5a9e4a494deb8ca6260.png)

1.  Go to the **Request** **Inspection** page and repeat the steps until you are
    comfortable with the inspection request process.

### Task 2: Record using app

Create a new desktop flow in the **Construction Funding** solution and record
the steps using the **Inspection** web app.

1.  Navigate to `https://make.powerapps.com/` and make sure you have the Dev
    environment selected.

1.  Select **Solutions** and open the **Construction Funding** solution.

1.  Click + New and select Automation - Desktop flow.

    ![new desktop flow](media/056cd93d8bdf1d1028edaa189a2f3bd0.png)

1.  Enter `Perform Site Inspection` for Flow name and click **Launch app**.

1.  Power Automate Desktop flow designer should launch. You may need to click
    **Open** on the browser to permit the action.

1.  Expand the **Browser automation** group and double click on the **Launch new
    Microsoft Edge** action.

1.  Provide [https://fabrikaminspectionstest.azurewebsites.net](https://fabrikaminspectionstest.azurewebsites.net/) for Initial URL and click **Save**.

    ![enter details as described](media/2589270f87f474e268f012fc80189634.png)

1.  DO NOT start recording yet.

1.  Minimize or close all but desktop flow application.

1.  Click **Run**.

    ![Run the flow](media/5a66a8d36ae17571f465053651386044.png)

1.  Microsoft Edge should load and navigate to the URL you provided.

1.  DO NOT close this Browser session.

1.  Go back to the desktop flow and click **Recorder**.

1.  The recorder pane should come to view.

1.  DO NOT start recording. Once you’ve reviewed the steps below, start
    recording. When you start recording you will repeat the steps you went
    through during the practice as outlined below.

    i. Go to the **Request Inspection** page.

    ii. Enter your name for **Inspection Account**

    iii. Enter `123 Main Street` for Property Address.

    iv. Enter `Test work item` for Work to Inspect.

    v. Click on the **Request Inspection** button.

    vi. Right click on the **Job Number** and select **Extract element value \|
    Text: ('your job number here')**. Remember the Job number.

    vii. Navigate to the Inspection Results page.

    viii. Provide your name again.

    ix. Enter the **Job number**.

    x. Click on the **Check Inspection** button.

    xi. Right click on the **Job status** and select **Extract element value \|
    Text: ('In progress')**.

    ![enter details as described](media/62ca14d1bd7106701ae97472ff5025ca.png)

    **Note**: Depending on your speed, the Job Status may already be **Completed**. In
    this case select corresponding option **Extract element value \| Text: ('In
    progress')**.

    xii. Go back to the recorder and click **Done**.

1.  Click **Record** and perform the steps.

1.  After you finish recording, your recorder actions should look like the image
    below.

1.  Click **Save** and wait for the flow to be saved.

    ![summary of completed work](media/2a1f885632001d5235d0408f47157895.png)

### Task 3: Add input and output variables

In this task, you will define the input and output variables that you'll use to
replace the hard coded values recorded. The input variables will be used to pass
data from the calling cloud flow. The output variables will be used to return
data to that flow.

1.  Open the **Variables** pane, click the plus button **(+)** and select
    **Input**.

2.  Enter `InspectionAccountNumber` for Variable name, select **Text** for
    Data type, `Jane Doe` for Default value, `InspectionAccountNumber` for
    External name, `Inspection account number` for Description, and click
    **Save**.

3.  Click **(+)** and select **Input** again.

4.  Enter `PropertyAddress` for Variable name, select **Text** for Data type,
    `123 Main Street` for Default value, `PropertyAddress` for External
    name, `Property address` for Description, and click **Save**.

5.  Click **(+)** and select **Input** one more time.

6.  Enter `WorkToInspect` for Variable name, select **Text** for Data type,
    `Test work item` for Default value, `WorkToInspect` for External name,
    `Work to inspect` for Description, and click **Save**.

7.  Click **(+)** and select **Output**.

8.  Enter `InspectionStatus` for Variable name, select **Text** for Data type,
    `InspectionStatus` for External name, `Inspection status` for
    Description, and click **Save**.

9.  Click **(+)** and select **Output** again.

10. Enter `SitePhotos` for Variable name, select **Text** for Data type,
    `SitePhotos` for External name, `Site photos` for Description, and click
    **Save**.

11. Click **(+)** and select **Output** one more time.

12. Enter `JobNumber` for Variable name, select **Text** for Data type,
    `JobNumber` for External name, `Job number` for Description, and click
    **Save**.

13. You should now have three input and three output variables.

### Task 4: Change to use variables

In this task, you will modify hard coded values in the steps to use the
variables you just defined.

1.  Go to the Populate text field on web page for the account number and double
    click on it.

    ![select the item as noted](media/c94d50b57a3c091db8ff5fd67992b5ca.png)

1.  Clear the Text value and click on the **{x}** select variable button.

    ![clear the value and select variable button](media/51d57b873da366800a8cd85a22de6847.png)

1.  Select **InspectionAccountNumber** and click **Select**.

1.  Click **Save**.

1.  Go to the Populate text field on web page for the property address and
    double click on it.

1.  Clear the Text value and click on the **{x}** select variable button.

1.  Select **PropertyAddress** and click **Select**.

1.  Click **Save**.

1.  Go to the Populate text field on web page for the work to inspect and double
    click on it.

    ![select item as noted](media/56c3ee69f4d47946a32998134f1be7b9.png)

1.  Clear the Text value and click on the **{x}** select variable button.

1.  Select **WorkToInspect** and click **Select**.

1.  Click **Save**.

1.  Go to the first Get details of element on web page and double click on it.

    ![select item as noted](media/d13479207d70c45c972c53d95509a14f.png)

1.  Click on the variable name, change it to **JobNumber**, and click
    **Save**. You are typing in this field.

    ![enter details as described](media/JobNumber_described.png)

1.  Go to the Populate text field on web page for the second account number and
    double click on it.

    ![select the item as described](media/dde5b0f0605eaae7dbd4d306e8de207a.png)

1.  Clear the Text value and click on the **{x}** select variable button.

1.  Select **InspectionAccountNumber** and click **Select**.

1.  Click **Save**.

1.  Go to the last Populate text field on web page and double click on it.

    ![select the item as described](media/8ab7905e03dcc9cf98a35de47a1cb1c3.png)

1.  Clear the Text value and click on the **{x}** select variable button.

1.  Select **JobNumber** and click **Select**.

1.  Click **Save**.

1.  Go to the last Get details of element on web page and double click on it.

    ![select the item as described](media/a408fd5e38bf221c80bca45a564a9c99.png)

1.  Click on variable and then click on the **{x}** select variable button.

1.  Select **InspectionStatus**.

1.  Click **Save** and close the Fabrikam Inspection website.

1.  If your Launch new Microsoft Edge is not the first action in the flow, then
    drag the Launch new Microsoft Edge action and drop it before all the
    recorded actions.

    ![order items as described](media/ba1579db3eb5cd315f39bf5a09e3032a.png)

1.  Click **Run** and wait for the run to complete.

1.  You should get an error similar to the one below. You see this error because
    the job number will be different for each run, but the flow is trying to
    match it with job number generated during the recording.

    ![job number error](media/e33f713bb81eca73bb83eff99e83c2be.png)

1.  Go the **UI elements** tab and double click on the **Table data cell
    'xxxxx'** UI.

    ![Table data cell](media/b37c211f5088cba330bb2eb8a5fab827.png)

1.  Select the last element form the **Elements** list **Table data cell
    'xxxxx'**, uncheck the **Text** attribute, check the **Ordinal** attribute,
    change the value or the Ordinal from 0 to **1**, and click **Save**. We are
    telling the flow to use the value in the second cell of the table, the table
    cells are zero based where 0 is the first cell and 1 is the second cell.

    ![UI element editor](media/43d423601a3f1a5008a42a9e86bed884.png)

1.  We will do the same thing for the inspection status. Double click on the
    **Table data cell 'In progress'** UI.

    Note: Depending on the recording previously, this might be **Table data cell
    'Completed'**.

    ![Table data cell](media/e5444a0fd04f49ca219166f7bae5b443.png)

1.  Select the **Table row 'Job Status: In progress** element, check the
    **Ordinal** attribute checkbox, enter 1 for the Ordinal value, and then
    select **Table data cell 'In progress'**. You are selectecting the row first
    and then moving to edit the cell.

    ![Table data row](media/e6033fd5c7b4848ca5b1be4fe9767406.png)

1.  Uncheck the **Text** attribute, check the **Ordinal** attribute, change the
    value or the Ordinal from 0 to **1**, and click **Save**.

1.  Run the flow again.

1.  The flow run should now succeed, and the variables should look like the
    image below.

    ![review the results](media/60844ff6ed2ba5ae899410be976699ab.png)

1.  Click **Save** and wait for the flow to be saved.

### Task 5: Add loop condition and wait control

In this task, you will be adding a loop to recheck if the inspection is done.
You will add a delay to give the inspection time to be completed before checking
again.

1.  Expand the **Loops** group, drag **Loop condition** and drop it before
    Populate text field on a web page for the second InspectionAccountNumber
    action.

    ![drag the item as described](media/1c672faf490476ab2a78d32cf698a1d7.png)

1.  Click on the **{x}** select variable button of the First operand.

    ![select variable as noted](media/be77ba0da8c098db07e9b7acee09ee47.png)

1.  Select **InspectionStatus** and click **Select**.

1.  Select **Not equal to (<\>)** for Operation, enter **Completed** for the
    Second operand, and click **Save**.

    ![enter details as described](media/93e54850b81291ccd13aee3f77fb6da0.png)

1.  Select the four actions after the loop and move them inside the loop by drag
    and drop.

    ![move the items as described](media/7156a00189da2823de7f9b069a1c749f.png)

1.  Expand the **Flow control** group, drag **Wait** action and drop it before
    the **End** loop.

    ![drag the item as described](media/05ee00bb91a134b885ef4f7352218b40.png)

1.  Enter **10** seconds and click **Save**.

1.  Click **Run** and wait for the flow to complete. The flow should go through
    the loop until the inspection status changes to **Completed**.

    ![review the results](media/15ca08e348275a0a45e06b0d9e13353e.png)

1.  Do not close the browser.

1.  Click **Save** and wait for the flow to be saved.

### Task 6: Use JavaScript to build JSON

In this task, you will use JavaScript to extract the work site inspection photos
and format the data into a JSON array that can be used to populate the output
variable.

1.  Go to the **Actions** pane and expand the **Browser automation** group.

2.  Expand the **Web data extraction** subgroup and double click on the
    **Extract data from web page** action.

    ![select the item described](media/bf76bbcc5fcb988a92536130e3f8218f.png)

1.  Go back to the web page, right click on the image, and select **Extract
    entire HTML table**.

    ![follow the steps](media/31c2f0593fa2dd9a4cf99b97228a3f30.png)

1.  Notice you only get Value \#1, currently, extract is not able to extract
    both columns of the table because column 2 is an img tag.

    ![review the results](media/7d6ffea9e35d9bb0fc224dc999f5abc3.png)

1.  Click **Cancel**.

1.  Click **Cancel** again.

    ![select cancel](media/9e63fb6a3c7f756485278be09d286363.png)

1.  Go to the web page and open the DevTools via the **F12** key. We are going
    to use Dev Tools to test our JavaScript.

1.  Select the **Console** tab and click **Clear console**.

    ![enter details as described](media/6f636d01d801e3712b47bc3630b46d36.png)

1.  Paste the script below and press enter.


    ```js
    var table = document.getElementById("sitephotostable");
    
    var sitephotolist = { images:[] }
    
    for (var i = 0; i < table.rows.length; i++) {
    
    row = table.rows[i];
    
    namecol = row.cells[0];
    
    imgcol = row.cells[1];
    
    var imgtags = imgcol.getElementsByTagName('img');
    
    var imgsource = imgtags[0]['src'];
    
    console.log(imgsource)
    
    sitephotolist.images.push({"name":namecol.innerText, "url":imgsource})
    
    }
    
    console.log(JSON.stringify(sitephotolist))
    ```


1.  Review the information you are trying to extract.

    ![review results](media/63db14226dc3be1f5456d1935854e8ee.png)

1.  Close the DevTools.

1.  Go back to the desktop flow.

1.  Expand the **Browser automation** group, drag **Run JavaScript function on a
    web page and get the returned result** action and drop it after the **End**
    loop.

    ![drag item as described](media/8bb6ee853fb082e3f03495b822257ecf.png)

1.  Select **%Browser%** for Web browser instance, paste the script below in the
    JavaScript function field, expand the **Variables produced** section, click
    on the **{x}** select variable button.

    ```js
    function ExecuteScript()

    {

    var table = document.getElementById("sitephotostable");

    var sitephotolist = { images:[] }

    for (var i = 0; i < table.rows.length; i++) {

    row = table.rows[i];

    namecol = row.cells[0];

    imgcol = row.cells[1];

    var imgtags = imgcol.getElementsByTagName('img');

    var imgsource = imgtags[0]['src'];

    console.log(imgsource)

    sitephotolist.images.push({"name":namecol.innerText, "url":imgsource})

    }

    console.log(JSON.stringify(sitephotolist))

    return JSON.stringify(sitephotolist);

    }
    ```    
    ![review the results of the script you added](media/dfbf01fcb86af2caf8574737a7ebf3a9.png)

15.  Select **SitePhotos**.

16.  Click **Save**.

17.  Expand the **Browser automation** group, drag **Close web browser** action,
    and drop it to the bottom of the recorded actions.

        ![drag the item as described](media/ab371f1d6af8cee5cfedac5e556511e5.png)

18.  Select **%Browser%** for web browser instance and click **Save**.

19.  Click **Save** and wait for the flow to be saved.

### Task 7: Close browser and test

1.  Close the Fabrikam Inspection website.

1.  Click **Run** and wait for the run to complete. The flow will loop through
    the loop condition multiple times, until the status changes to completed.

1.  Go to the Variables pane and make sure the **SitePhotos** variable has the
    expected value.

    ![review results](media/e72e525c9a174636301924f5cdbebf4a.png)

1.  Click **Save** and wait for the flow to be saved.
