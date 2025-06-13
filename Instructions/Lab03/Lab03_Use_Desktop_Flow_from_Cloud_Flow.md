---
lab:
    title: 'Lab 3 - Use Desktop Flow from Cloud Flow'
    module: 'Module 3 - Use Desktop Flow from Cloud Flow'
---

# Using Desktop Flows from Cloud Flows

## Scenario

In this lab, you will build cloud flows which integrate with the desktop flows.

## High-level lab objectives

-   Use child flows to create a more maintainable cloud flow

-   Use desktop flows from cloud flow

## Exercise 1: Lookup Loan Child flow

### Task 1: Create child flow

1.  Navigate to `https://make.powerapps.com/` and make sure you are in the Dev
    environment.

1.  Select **Solutions** and open the **Construction Funding** solution.

1.  Click **+ New** and select **Automation \| Cloud flow \| Instant**.

    ![Select new instant flow](media/31a6dc86c4a9153b5c7a346a755a5117.png)

1.  Enter `CF Lookup Loan` for Flow name, select **Manually trigger a flow**,
    and click **Create**.

    ![Name the flow and select manual trigger](media/4a5adb7e114267266a0e4eae524091d1.png)

1.  Expand the trigger by clicking on **Manually trigger a flow**.

1.  Select **+ Add an input**.

    ![select add an input](media/9fb73770069eec9c06a8cbaa9938d669.png)

1.  Select **Text**.

1.  Enter `LoanNumber` and click **+ New step**.

    ![add LoanNumber and select new step](media/eb3f11c6bdfabfca5b4bad9d21b66f5c.png)

1.  Search for list rows and select **List rows Microsoft Dataverse**.

    ![search for and select List rows for Microsoft Dataverse](media/74fb1c354d46359f4c425bbceff61cd7.png)

1.  Select **Loans** for Table name and click **Show advanced options**.

    ![Show advanced options](media/Loan_showadvancedoption.png)

1.  Enter `rc_loannumber eq` for Filter rows and select **LoanNumber** from
    the dynamic content pane.

    ![enter details listed](media/527d6b2e80ebda324d6fb289dedb960c.png)

     If you do not see the **Dynamic Content & Expression** pop-up, increase
your browser width or zoom out slightly to reveal it (Keyboard shortcut: Ctrl +
\-).

1.  Add single quotes (') before and after LoanNumber

1.  Click **+ New step**.

1.  Select **Condition**.

    ![add the condition](media/52c4030d5688332d0ed6fdc0056d1b6c.png)

1.  Click to select the first operand field, go to the dynamic content pane, and
    select the expression tab.

1.  Paste the expression below and click **OK**. This checks if any rows were
    returned.
    ```
    empty(outputs('List_rows')?['body/value'])
    ```
    ![paste the expression listed](media/6e38a01ee8548edede0979ce18abb9ec.png)

1.  Select **is equal to** for condition.

1.  Click to select the second operand field, go to the dynamic content pane,
    and select the expression tab.

1.  Type **true** and click **OK**.

    ![add the true item](media/9a3bf0f797301750ad7a446af00cf5d0.png)

1.  Go to the **If yes** branch and click **Add an action**.

    ![add an action in the yes branch](media/25570bc5d2547c01b594033e65ea4fad.png)

1.  Select **Respond to a PowerApp or flow**.

    ![search for and select the Respond to a PowerApp or flow action](media/e7594839c52a95d2191d466a68f9a00a.png)

1.  Click **+ Add an output**.

    ![select add an output](media/0c440556eec800d7a841665372667dc1.png)

1.  Select **Yes/No**.

1.  Enter `LoanFound` for title and click to select the value field.

1.  Go to the Dynamic content pane and select the **Expression tab**.

1.  Type **false** and click **OK**.

    ![type false for the function and select ok](media/76e07ff3a7c8d3aba23f7f9a0b39d120.png)

1.  Click **+ Add an output** again.

1.  Select **Text**.

1.  Enter `LoanID` for title.

1.  Click on the value field, add an empty space.

    ![place your curser in the empty space as described](media/c65b9c37b51edcca41addefa2b9a169b.png)

1.  Click on the **…** more actions button and select **Rename**.

    ![in more actions, select rename](media/1dbbae3e15fbe49aecbd5f3ca356a23b.png)

1.  Rename the step `Not found response`.

1.  Go to the **If no** branch and click **Add an action**.

    ![add an action in the no branch](media/67bd65d51399702a25eae91b8214d263.png)

1.  Select **Respond to a PowerApp or flow**.

    ![search for and select respond to a PowerApp of flow action](media/e7594839c52a95d2191d466a68f9a00a.png)

1.  Click **+ Add an output**.

1.  Select **Yes/No**.

1.  Enter `LoanFound` for title and click to select the value field.

1.  Go to the dynamic content pane and select the **Expression tab**.

1.  Type **true** and click **OK**.

    ![enter the value true for the function](media/8194136ead3b19b2dbcef80ab6e0caea.png)

1.  Click **+ Add an output** again.

1.  Select **Text**.

1.  Enter `LoanID` for title.

1.  Click to select the value field, go to the dynamic content pane, and select
    the **Expression** tab.

1.  Paste the expression below and click *OK*. This gets the ID from the first
    row.
    ```
    first(outputs('List_rows')?['body/value'])?['rc_loanid']
    ```
    ![paste the expression as directed](media/0a2db53893bda42099db6138cad1b0cf.png)

1.  Click on the … more actions button and select **Rename**.

1.  Rename the step `Found response`.

1.  Click **Save** to save the flow.

    ![save the flow](media/9aeb5c68f2a76eee529c28b744d0dbf3.png)

1.  Click **Test**.

    ![test the flow](media/babdc333dbe8b1886f60d6b5757e5b6b.png)

1.  Select **Manually** and click **Test**.

1.  Enter `MC3747` for LoanNumber and click **Run flow**.

    ![give the load number MC3747](media/8c00408424f03051f3076257b848e219.png)

1.  Click **Done**.

1.  Click to expand the response step.

1.  Make sure the output body matches your expectation.

    ![verify the output](media/47b74bc51187be29ff4e3182e00c2b61.png)

1.  You may close the flow

## Exercise 2: Inspection Child flow

### Task 1: Setup Machine connection

1.  Navigate to `https://make.powerapps.com/` and make sure you are in the Dev
    environment.

1.  Select **Solutions** and open the **Construction Funding** solution.

1.  Click **+ New** and select **More \| Connection Reference**.

    ![in the solution select new connection reference](media/71674a96b84d726cb7477be4399b6d28.png)

1.  Enter `Desktop Flows` for Display name, select **Desktop flows** for Connector,
    click on the Connection dropdown and select **+ New connection**.

    ![select new connection](media/7a65d3b69202924ab6b77996677f907b.png)

1.  Select **Connect with username and password** for Connect and select your
    desktop. If you don’t see your desktop here, go to desktop flow machine
    settings and make sure you have the Dev environment selected.

    ![set the connections for the desktop flow](media/da15e5177fe8a3534c36e4d0572fc1de.png)

1.  Provide your Machine/VM admin username and password, and click **Create**.

    ![provide user information](media/0321ff34a66de83c0127f1b61f1338cc.png)

1.  Close the connection browser tab or window.

1.  Click on the **Refresh** connection button.

    ![refresh the connection](media/215b14b3d347300e60ad43ea51ef5ede.png)

1.  Select the connection you created and click **Create**.

    ![select create](media/3e59930f39709f70a8c99c55da3ddc48.png)

### Task 2: Create child flow

1.  Navigate to `https://make.powerapps.com/` and make sure you are in the Dev
    environment.

1.  Select **Solutions** and open the **Construction Funding** solution.

1.  Click **+ New** and select **Automation \| Cloud flow \| Instant**.

    ![add a new instant flow automation to the solution](media/0cb928da96f8fd274bc056e952146085.png)

1.  Enter `CF Manage Inspection Process` for Flow name, select **Manually
    trigger a flow**, and click **Create**.

1.  Expand the trigger and click **+ Add an input**.

1.  Select **Text**.

1.  Enter `PropertyAddress` and click **+ Add an input** again.

    ![enter details as listed](media/6e20fb341d44a0687ab9adcb97aca4a5.png)

1.  Select **Text**.

1.  Enter `LoanDrawID` and click **+ Add an input** one more time.

1.  Select **Text**.

1.  Enter `Work`. You should now have three input parameters. Click + New
    step.

    ![enter details as listed](media/4ced57e4f25dc925a24d32c3d115062b.png)

1.  Select **Run a flow built with Power Automate for desktop**.

    ![search for and select Run a flow built with Power Automate for desktop](media/193cffad3ac95dc5989b473cea694a8b.png)

1.  Select **Perform Site Inspection** for Desktop flow and select **Attended**
    for Run Mode.

1.  Click on the **WorkToInspect** field and select **Work** from the dynamic
    content pane.

    ![select work from the dynamic content pane](media/c05b976be9b1525c64cb2a5e35a468d5.png)

1.  Click on the **PropertyAddress** and select **PropertyAddress** from the
    dynamic content pane.

1.  Enter your name for Inspection account number.

    ![enter text as described](media/69305a1cbd5a03377d8e055bfd38e3ad.png)

1.  Click **+ New step**.

1.  Search the connectors and actions for **Parse JSON**. Select the **Parse
    JSON** action which is part of the **Data Operation** connector.

    ![select parse JSON](media/33f1eb359d738c92ca16455e6a7ec233.png)

1.  Click on the **Content** field and select **SitePhotos** from dynamic
    content pane.

    ![select SitePhotos from dynamic content pane](media/07ffd505279418b1be6f6d5d4f87b12d.png)

1.  Paste the JSON schema below in the **Schema** field and click **+ New
    step**. Typically, you would generate this from a sample of the data
    expected.

    ```json
    {
       "type":"object",
       "properties":{
          "images":{
             "type":"array",
             "items":{
                "type":"object",
                "properties":{
                   "name":{
                      "type":"string"
                   },
                   "url":{
                      "type":"string"
                   }
                },
                "required":[
                   "name",
                   "url"
                ]
             }
          }
       }
    }
    ```


    ![select new step](media/00b654648148176b62ee179ca99dcb86.png)

1.  Select the **HTTP** action.

    ![A screenshot of a computer Description automatically generated](media/d70573a85eba227f52d75485a5365592.png)

1.  Select **GET** for Method, click on the **URI** field, and select **url**
    from the dynamic content pane.

    ![select Get method](media/8a88c0cb739070c7adfbc01c9ae05e1d.png)

1.  Apply to each will be added automatically for you. Rename the Apply to each
    step **Apply to each image**.

1.  Click **Add an action**.

    ![select add an action from the apply to each image step](media/0d6e2127a79af494545e1e42908012d0.png)

1.  Select the **Add a new row** action from the **Microsoft Dataverse**
    connector.

    ![search for and select Add a new row action](media/65995cfb9c9dd8cb3b42509f18ad06b7.png)

1.  Select **Inspection Photos** for Table name, click on the **Name** field,
    and select **name** from the dynamic content pane.

    ![choose Inspection Photo and enter the details](media/416894dc73d22d4f0a83a656a3ea7fe7.png)

1.  Rename the Add a new row step to **Add inspection photo** and click **Show
    advanced options**.

    ![rename the step](media/465946d44f7b4800b294065ea4a7d048.png)

1.  Enter `rc_loandraws()` for Loan Draw, place your cursor inside the
    parentheses, and select **LoanDrawID** from the dynamic content pane.

    ![enter details shown](media/94d07caa42a94430882151eb9906f69e.png)

1.  Click on the **Photo** field, go to the dynamic content pane, and select the
    **Expression** tab.

1.  Paste the expression below and click **OK**.

    `base64(body('HTTP'))`

    ![enter details shown](media/eb65ad30d8c787e2986f85fbce694c25.png)

1.  Click **+ New step**.

    ![select add new step](media/e314d40650917e36507117cb9e5be1ad.png)

1.  Select the **Update a row** action from the **Microsoft Dataverse**
    connector.

    ![search for an select Update a row Microsoft Dataverse](media/2b97189790a555470e1045ca726e029e.png)

1.  Select **Loan Draws** for Table name, click on the **Row ID** field and
    select **LoanDrawID** from the dynamic content pane.

1.  Click **Show advanced options**.

    ![show advanced options](media/b05202d48ec029a0586f55639afdd9d9.png)

1.  Click on the **Inspected On** field, go to the dynamic content pane, select
    the **Expression** tab, type **utcNow()** and click **OK**.

    ![add time to the field](media/80f425d3da70c60885cc5cc308aaa6cf.png)

1.  Click on the **Inspection Job** field and select **JobNumber** from the
    dynamic content pane.

    ![add job number field](media/534353f9b289b06f1e5edc83c6ba6490.png)

1.  Select **Inspection Completed** for Status Reason and click **Hide advanced
    options**.

    ![input status reason and hide advanced options](media/8380a989e711f5ae72787c33e19b4be8.png)

1.  Rename the step **Update loan draw** and click **+ New step**.

1.  Select the **Respond to PowerApp or flow** action from the **PowerApps**
    connector.

    ![search for and select Respond to PowerApp or flow](media/b4bf7a3d4d0438cda6621781a04a0024.png)

1.  Click **+ Add an output**.

1.  Select **Text**.

1.  Enter `InspectionStatus`, click on the value field and select
    **InspectionStatus** from the dynamic content pane.

    ![enter details as described](media/59177ca95f2f487ac4c418ea8328f02b.png)

1.  Click **+ Add an output** again.

1.  Select **Text**.

1.  Enter `JobNumber`, click on the value field and select **JobNumber** from
    the dynamic content pane.

    ![enter details as described](media/e51276a6978f59b36e463384518f2320.png)

1.  Click **Save** to save the flow.

1.  Click on the **back** arrow.

    ![select back button](media/eec0ed3e01dacef6ed46fdaedd8663dc.png)

1.  Open the flow details.

    ![open flow details](media/d93800afb6272d52b4e96f2cd156024d.png)

1.  Click **Run**.

1.  If prompted, select **Manually** and click **Test** again.

1.  Click **Continue**.

    ![run the flo](media/41eb830c1d4da67216e618327a2805e2.png)

1.  **DO NOT** navigate away from this page.

1.  Start a new browser instance and navigate to <https://make.powerapps.com/>
    and make sure you are in the Dev environment.

1.  Select **Apps** and launch the **Loan Manager** application.

    ![launch the loan manager app](media/cb1fed8bf74d5ff4fa7dbabf3a8950a7.png)

1.  Open the first loan record.

1.  Click **Related** and select **Loan Draws**.

    ![drill into record details as described](media/75161237e002948e264661953147ee6a.png)

1.  Click **+ New Loan Draw**.

    ![add a new loan draw](media/b6b770c3e589323334d9cd4e915ed1ad.png)

1.  Enter `Test Draw` for Name and click **Save**.

1.  Go to the URL and copy the **id** GUID. Paste this id into Notepad, you will
    need it in future steps.

    ![get the url id as described](media/6a800d728a8597239b81341ffe9280db.png)

1.  Go back to the Cloud Flow and enter `123 Main Street` for PropertyAddress,
    paste the id you copied in the LoanDrawID field, type `Test work item` for
    Work, and click **Run flow**.

    ![follow the steps to run the flow](media/34461abf8954b9e607a962cb99d4fb7c.png)

1.  **Wait** for the flow run to complete.

1.  **Close** the run flow pane.

1.  Go to the **28-day run history** and click **refresh** until the flow run
    shows as **Succeeded**.

    ![Wait for the succeeded message](media/cc44924af45b89cda154bb434ef650ff.png)

1.  Go back to the **Loan Manager** application, click **Related** and select
    **Inspection Photos**.

    ![Select the related photos](media/244cfcc90486d286239346b69a16d1a9.png)

1.  You should see the inspection photos created by the flow.

    ![Review the photos created by the flow](media/1ca014f80497723503c72b5f0ab029c3.png)

## Exercise 3: Funding Child flow

### Task 1: Create child flow

1.  Navigate to `https://make.powerapps.com/` and make sure you are in the Dev
    environment.

1.  Select **Solutions** and open the **Construction Funding** solution.

1.  Click **+ New** and select **Automation \| Cloud flow \| Instant**.

1.  Enter `CF Manage Woodgrove Funding Process` for Flow name, select
    **Manually trigger a flow**, and click **Create**.

    ![name your new flow](media/f2aeb022cdb810c1f27410796e609160.png)

1.  Expand the trigger and click **+ Add an input**.

    ![select add input](media/d0f02400314063231e7a994548ca7da4.png)

1.  Select **Text**.

1.  Enter `LoanNumber` and click **+ Add an input** again.

1.  Select **Text**.

1.  Enter `LoanDrawID` and click **+ Add an input** again.

1.  Select **Text**.

1.  Enter `RequestedAmount` and click **+ Add an input** again.

1.  Select **Text**.

1.  Enter `InspectionJobID` and click **+ Add an input** again.

1.  Select **Number**.

1. Enter `RiskScore`.

1. You should now have five inputs. Click **+ New step**.

    ![review the steps and select new step](media/1b915f0e63e2f032ec554ba3ff241eda.png)

1.  Select the **Run a flow built with Power Automate for desktop** action.

    ![Search for and select the Run a flow built with Power Automate for desktop action](media/883f4f95c9b5b2e4c6bf560bc4edb4b5.png)

1.  Select **Woodgrove Funding Manager Draw** for Desktop flow and select
    **Attended** for Run Mode.

1.  Click on the **LoanNumber** field and select **LoanNumber** from the dynamic
    content pane.

    ![follow the steps for using the dynamic content pane](media/ccf427cdd940bcdbc46c38770cac7c46.png)

1.  Click on the **RequestedAmount** field and select **RequestedAmount** from
    the dynamic content pane.

1.  Click on the **InspectionJobNumber** field and select **InspectionJobID**
    from the dynamic content pane.

1.  Type **Yes** for BorrowerApproved.

1.  Click on the **RiskScore** field and select **RiskScore** from the dynamic
    content pane.

1.  Enter your name for Username, `pass@word1` for Password.

1.  The run desktop flow should now look like the image below. Click **+ New
    step**.

    ![review the steps](media/162069ca1157b78db0a5599c009ec42d.png)

1.  Select the **Condition** action from the **Control** connector.

1.  Click on the first operand and select **FundingStatus** from the dynamic
    content pane.

    ![add details to the funding step](media/c895effc56789b1d07ebc1bfb3dc2e83.png)

1.  Select **is equal to** for operator and enter `Approved` for the second
    operand.

1.  Go to the **If yes** branch and click **Add an action**.

    ![add an action to the yes side](media/7ed60f6d50492df31d1ff11f460996e2.png)

1.  Select the **Update a row** action from the **Microsoft Dataverse**
    connector.

    ![select update a row for Dataverse](media/e7d4c43e8d48bc0a81d425d27cd44c09.png)

1.  Select **Loan Draws** for Table name, click on the Row ID field and select
    **LoanDrawID** from the dynamic content pane.

    ![select loan draw for table](media/a5bc56e6ca8a5a1edcd9e70d58c2d73b.png)

1.  Click **Show advanced options**.

1.  Click on the **Amount Funded** field and go to the dynamic content pane and
    select the **Expression** tab.

1.  Paste the expression below and click **OK**.
    ```
    replace(outputs('Run_a_flow_built_with_Power_Automate_for_desktop')?['body/FundedAmount'],'$','')
    ```
    ![paste the expression](media/4d6f9860edd9ef4e754562116d70395d.png)

1.  Click on the **Funded On** field, go to the dynamic content pane, and select
    the **Expression** tab.

1.  Type **utcNow()** and click **OK**.

    ![add time field](media/7a1852199cc7f9996af339bcd8ccf01b.png)

1.  Click on the **Funding Sequence Number** field and select
    **FundSequenceNumber** from the dynamic content pane.

1.  Click on the **Funding Transfer Number** field and select
    **FundTransferNumber** form the dynamic content pane.

1.  Click on the **RiskScore** field and select **RiskScore** form the dynamic
    content pane.

1.  Select **Funding Approved** for Status Reason and click **Hide advanced
    options**.

    ![set status reason](media/3c2b66789a2cca473f6cc5035a8529dc.png)

1.  Rename the step **Update for approved**.

1.  Go to the **If no** branch and click **Add an action**.

    ![add an action on the no branch](media/df31110ddeb822a6e9f91d71b97b85e7.png)

1.  Select the **Update a row** action from the **Microsoft Dataverse**
    connector.

    ![select update a row](media/e7d4c43e8d48bc0a81d425d27cd44c09.png)

1.  Select **Loan Draws** for Table name, click on the Row ID field and select
    **LoanDrawID** from the dynamic content pane.

    ![select loan draws](media/cc374dc98f623681f7ff369b9feb4c08.png)

1.  Click **Show advanced options**.

1.  Select **Funding Denied** for Status Reason and click **+ New step**.

    ![set status reason](media/44b93644132ca888528646e4dcd68ef9.png)

1.  Select the **Respond to PowerApps or flow** action from the **PowerApps**
    connector.

    ![select respond to PowerApp or flow action](media/2a49f75f5dae33f58690f239f5f35556.png)

1.  Click **+ Add an output**.

1.  Select **Text**.

1.  Enter `FundingStatus`, click on the value field and select
    **FundingStatus** from the dynamic content pane.

    ![enter details as described](media/732f3352b8f02a78511c4b31dce21408.png)

1.  Click **Save** and wait for the flow to be saved.

1.  Click **Test**.

1.  Select **Manually** and click **Test** again.

1.  Click **Continue**.

1.  Enter `JG7165` for LoanNumber, paste the id you copied in the previous
    exercise for LoanDrawID, enter `80000` for RequestedAmount, enter `123`
    for InspectionJobID, enter `50` for RiskScrore, and click **Run flow**.

    ![run the flow with the provided details](media/runaflow_cf_manage_woodgrove.png)

1.  **Wait** for the flow run to complete, the flow run should succeed. Click
    **Done** to review the flow run history.

## Exercise 4: Build Overall Process Flow

### Task 1: Create a shared mailbox

1.  Navigate to `https://admin.microsoft.com/` and click **Show all**.

    ![in the admin portal, select show
all](media/deed82ec8c0efea0fb41c7f21be2ec8e.png)

1.  Go to the **Admin centers** area and select **Exchange**.

    ![select exchange](media/9bfe4fb8721fba249fad0f2d68b507d9.png)

1.  In the left side menu under **Recipients** select **Mailboxes**.

1.  Click **+ Add a shared mailbox**.

    ![add a shared mailbox](media/03c1b9ec7dadcbdf132ffca9d87ac366.png)

1.  Enter `Funding` for Display name, **Funding** for Email address, select
    your domain, and click **Create**.

    ![enter details as described](media/74f774357b9f8c0db5a18a5adabbbd41.png)

1.  Click **Add users to this mailbox**.

    ![add users to mailbox](media/aba25112d1bd9946855ce7f0f26ad3b1.png)

1.  Click **+ Add members**.

1.  Select your user and click **Save**. You may add other users to the shared
    mailbox.

    ![manage mailbox members](media/620ae9728cde52a5f7e1a0d0e1cf6835.png)

1.  Click **Confirm**.

1.  Close the shared mailbox pane.

## Task 2: Create flow

1.  Navigate to `https://make.powerapps.com/` and make sure you are in the Dev
    environment.

1.  Select **Solutions** and open the **Construction Funding** solution.

1.  Locate and open the **CF Manage Inspection Process** child flow.

    ![locate the child flow](media/df51c582c7b33f37487f525f5e899b04.png)

1.  Go to the **Run only users** section and click **Edit**.

    ![edit users](media/02834755365aceb0803a9a01ad89cfc5.png)

1.  Select the desktop connection you created and click **OK** on the popup.

1.  Click **Save**.

    ![select desktop flows](media/e2ee038d6ee9c15090273a8e0dfbe7f8.png)

1.  Click on the browser back button.

1.  Locate and open the **CF Manage Woodgrove Funding Process** child flow.

    ![open the next child flow](media/be4596c1956b1ce6660270676751a460.png)

1.  Go to the **Run only users** section and click **Edit**.

1.  Select the desktop connection you created and click **OK** on the popup.

1.  Click **Save**.

1.  Click on the browser back button.

1.  Click **+ New** and select **Automation \| Cloud flow \| Automated**.

    ![select automated](media/e1a3a64eaba280cb401a9576d4bf72be.png)

1.  Enter `Process Construction Funding Request` for Flow name, select the
    **When a new email arrives in a shared mailbox** trigger, and click
    **Create**.

    ![name and create the flow](media/d548f718a2f039b6969a770ee39a2665.png)

1.  Select the **Funding** shared email you created for **Original Mailbox
    Address**, select **Inbox** for Folder, and click **Show advanced options**.

1.  Select **Yes** for Include attachments and click on the **…** button of the
    trigger.

    ![select the ellipses ](media/d41f72effa5d7ca61a8f929196c35a21.png)

1.  Select **Rename**.

1.  Rename the trigger to **When a new funding request email arrives**.

1.  Click **+ New step**.

1.  Select the **Run a Child Flow** action from the **Flows** connector.

    ![select run a child flow action](media/4aeb178ea489ba833b9de74be2f8c804.png)

1.  Select **CF Lookup Loan** for Child flow.

1.  Click on the **LoanNumber** field, go to the dynamic content pane, and
    select **Subject**.

    ![enter details as described](media/100a3a1bee9065b8e17a6b110e397184.png)

1.  Rename the step **Lookup loan number**.

1.  Click **+ New step**.

1.  Select the **Condition** action from the **Control** connector.

1.  Click to select the first operand field, go to the dynamic content pane, and
    select **LoanFound**.

    ![enter details as described](media/ef9c8888838e7c2017e7649f728ddc25.png)

1.  Select **is equal to** for the operator and type True for the second operand
    field.

1.  Rename the condition **Check if loan number found**.

1.  Go to the **If no** branch and click **Add an action**.

1.  Select the **Send an email from a shared mailbox (V2)** action from the
    **Office 365 Outlook** connector.

    ![select send email from shared mailbox v2](media/9751f336fda9c92572379fb93e86e9cc.png)

1.  Click on the **Original mailbox Address**, click **Add dynamic content** and
    select **To** from the dynamic content pane.

    ![enter details as described](media/dcbf668bb972e848308be31201833d9c.png)

1.  Click on the **To** field, click **Add dynamics content** and select
    **From** from the dynamic content pane.

1.  Type `Loan number not found` for Subject.

1.  Type `Loan \#` Body and select **Subject** from the dynamic content pane.

    ![enter details as described](media/42004a70cc560c10b729d949fb0ec55c.png)

1.  Add `not found, contact your bank.` to the body.

1.  Rename the reply **Send loan not found email** and click **Add an action**.

    ![enter details as described](media/ea98fcbbbea26997b020baf847784968.png)

1.  Select the **Terminate** action from the **Control** connector.

    ![select terminate action](media/0a83994e8f090fe259cf27818f636db7.png)

1.  Select **Succeeded** for Status.

1.  Click **+ New step**.

    ![select new step](media/aad5f10df00a2f9d480caa56ed6178d6.png)

1.  Select the **Add a new row** action from the **Microsoft Dataverse**
    connector.

    ![select add a new row](media/00b733ce52cded147caa07c2dace2cff.png)

1.  Select **Loan Draws** for Table name.

1.  Enter **Loan draw** for Name and click **Show advanced options**.

    ![enter details as described](media/04b847fc231a060c86f153e9d699fa63.png)

1.  Enter `80000` for Amount Requested.

1.  Type **rc_loans()** for Loan (Loans), place your cursor inside the
    parentheses, and select **LoanID** from the dynamic content pane.

    ![enter details as described](media/105bb2261e9191687c0bdafe02361576.png)

1.  Rename the step **Create new loan draw row**.

1.  Click **+ New step.**

1.  Select the **Run a Child Flow** action from the **Flows** connector.

1.  Select **CF Manage Inspection Process** for Child flow.

1.  Enter `123 Main Street` for PropertyAddress.

1.  Click on the **LoanDrawID** field and select **Loan Draw** from the dynamic
    content pane.

    ![enter details as described](media/3795b1d1da9b36ba5867f52c2c2336e2.png)

1.  Enter `Test work item` for Work.

1.  Rename the child flow **Run inspection process** and click **+ New step**.

    ![rename the flow and select add new step](media/607f9fb11ca05f2673f213a231ebf410.png)

1.  Select the **Run a Child Flow** action from the **Flows** connector.

1.  Select **CF Manage Woodgrove Funding Process** for Child flow.

1.  Click on the **LoanNumber** field and select **Subject** from the dynamic
    content pane.

1.  Click on the **LoanDrawID** field and select **Loan Draw** from the dynamic
    content pane.

1.  Enter `80000` for RequestedAmount.

1.  Click on the **InspectionJobID** field and select **JobNumber** from the
    dynamic content pane.

1.  Enter `55` for **RiskScore**.

1.  Rename the child flow **Run funding process**. Click **Save**.

1.  Click **+ New step**.

    ![click new step](media/d123050cedcd9516142cc5a4b1d6d0fd.png)

1.  Select the **Condition** action from the **Control** connector.

1.  Click on the first operand and select **FundingStatus** from the dynamic
    content pane.

    ![enter details as described](media/84570d7d1d6471656b5ce4d7117d7d9e.png)

1.  Select **is equals to** for operator and enter **Approved** for the second
    operand.

1.  Rename the condition **Check approval status**.

1.  Go to the **If yes** branch and click **Add an action**.

    ![add an action on the yes branch](media/4586a0049f214916ffa64adfa16db561.png)

1.  Select the **Send an email from a shared mailbox (V2)** action from the
    **Office 365 Outlook** connector.

1.  Click on the **Original Mailbox Address** field, click **Add dynamic
    content** and select **To** from the dynamic content pane.

1.  Click on the **To** field, click **Add dynamics content** and select
    **From** from the dynamic content pane.

1.  Enter `Draw Approved` for Subject.

1.  Type `Your draw for` in the Body and select **Amount Funded** from the
    dynamic content pane.

    ![enter details as described](media/ba48a6e9f575b1444399956487be9f1a.png)

1.  Add `was approved` to the body.

1.  Rename the step **Send approved draw email**.

1.  Go to the **If no** branch and click **Add an action**.

    ![add an action to the no branch](media/d39e39e21828f106017725a0d13c55be.png)

1.  Select the **Send an email from a shared mailbox (V2)** action from the
    **Office 365 Outlook** connector.

1.  Click on the **Original Mailbox Address** field, click **Add dynamic
    content** and select **To** from the dynamic content pane.

1.  Click on the **To** field, click **Add dynamic content** and select **From**
    from the dynamic content pane.

1.  Enter `Draw was not approved` for Subject.

1.  Type `Your draw for` in the Body and select **Amount Funded** from the
    dynamic content pane.

1.  Add `was not approved, please contact bank.` to the body.

1.  Rename the step **Send draw not approved email**.

1.  Click **Save** and wait for the flow to be saved.

    ![save the flow](media/d7f69a2991886dc3abea49f7244ea49d.png)

### Task 3: Test flow

1.  Click **Test**.

1.  Select **Manually** and click **Test** again.

1.  Send an email with the subject **MC3747** from your email to the Funding
    shared email you created
    ([Funding@yourdomain.onmicrosoft.com](mailto:Funding@yourdomain.onmicrosoft.com)).

1.  Wait for the flow to get triggered. Do not interact your computer while the
    flow is running.

1.  The flow should run successfully.

    ![review the tested flow](media/d8f41d65bb9815d947e068e6465808dd.png)

1.  You should receive an email with the subject **Draw Approved**.
