**Integrate AI**

**Scenario**

In this lab, you will be using the AI Builder to process the construction
funding request form document that was emailed to the funding shared mailbox to
extract essential information. The extracted information will be stored in
Dataverse for use in the funding process.

**High-level lab steps**

-   Use sample request forms to train an AI Builder model

-   Modify the cloud flow to use the model to process the inbound document

-   Store the extracted information in the Loan Draw table

**Exercise \#1: Train model for request form**

In this exercise, you will create an AI Builder model that will process the
funding request form.

**Task \#1: Create AI Builder model**

1.  Go to the lab resources folder and open the **Train** folder.

2.  Click to open **Jim Glynn.pdf**.

![select the pdf in file explorer](media/8e530428b72e172827d45183c38e136e.png)

1.  The documents from which the model will extract the data will look like this
    document. Keep this file open, you will need it during model creation.

![review the document](media/350b676210cd8c18a068ed9daad5ae2c.png)

1.  Navigate to <https://make.powerapps.com/> and make sure you are in the Dev
    environment.

2.  Click **... More** and select **Discover all**.

![Select discover all](media/c510f3d64df649bdd98db8c4dc576d5b.png)

1.  Under AI select **Ai models**.

![Select AI models](media/7c02d33f0ea540be17d9a8dbeb250f97.png)

1.  Select **Extract custom information from documents**.

![Choose document processing](media/01afc012e03f58e58c0085c4888a3f58.png)

1.  Click **Create custom model**.

2.  Select **Structured documents** and click **Next**.

![select as described](media/6cfe5241425e51b3a3e9023723c30721.png)

1.  Do not navigate away from this page.

2.  Go to the **Jim Glynn** pdf fie, you will create fields and a table in the
    model that match the fields and the table in this document.

![select as described](media/0740eee464461c0c7c8e62d88d1de3d8.png)

1.  Go back to the model. Click the chevron button on the **+ Add** button and
    select **Text field**.

![select as described](media/ea41ee12ac015323e85b2bee5db22fd0.png)

1.  Enter **Owner Name** and click **Done**.

![enter details as described](media/ede072b9cbacfba26ce7400ba08ff2c2.png)

1.  Select the **+ Add** button and select **Text field** again.

2.  Enter **Property Address** and click **Done**.

3.  Select the **+ Add** button and select **Text field**.

4.  Enter **Builder Name** and click **Done**.

5.  Select the **+ Add** button and select **Text field**.

6.  Enter **Draw Amount** and click **Done**.

7.  Select the **+ Add** button and select **Text field** one more time.

8.  Enter **Loan Number** and click **Done**.

9.  You should now have five text fields added.

![review the resulting screen](media/9bec9d2d4a744491a6190e3c6086bad7.png)

1.  You will now add the table details. Click the chevron button on the **+
    Add** button and select **Table**.

![select as described](media/e7a2cfdb84ad0bd80b24c1969c06c1c5.png)

1.  Enter **Budget Items** for Table name.

2.  Click on **Column 1** and select **Edit column**.

![select as described](media/50e594f0d5d4eb73184cb4308f4587be.png)

1.  Enter **Budget Category** and click **Comfirm**.

![enter details as described](media/9e256794d83516b994cf807705a4ed42.png)

1.  Click **+ New column**.

![select as described](media/ea0cfa38dbdc8a0dd2a49b72babfda68.png)

1.  Enter **Amount** for Name and click **Add**.

2.  Your table should now have 2 columns. Click **Done**.

![review the results](media/bffceea00f8dfd54d7bfe11a60df46a2.png)

1.  Click **Next**.

2.  Do not navigate away from this page.

**Task \#2: Add sample documents**

1.  Click **New collection.**

![select as described](media/4c8adb8fe3a7a08c80a75c2c9b4b4c9d.png)

1.  Enter **Sample documents** for collection name and click **+** add.

![select as described](media/74736ea2860367f68dd7589328661bad.png)

1.  Click **Add documents**.

2.  Select **My device**.

3.  Select all **5** PDF files located in the **Train** folder and click
    **Open**.

![select the files](media/f6d4e2d582de0420fb46747bac4a9425.png)

1.  Click **Upload 5 documents** and wait for the files to be loaded.

2.  Click **Done**.

![confirm the selection](media/ed8203da524cb29790ca3474c2cdcdf9.png)

1.  Click **Next**.

2.  Do not navigate away from this page.

**Task \#3: Tag documents**

1.  Click on the name of the owner and select **Owner Name** as text field.

![select as described](media/805bffcccf95c11a2c427f24d104d80c.png)

1.  Select on the address and select **Property Address** as text field.

![select as described](media/0a972b31d98ec0990b060ba64b3993b0.png)

1.  Select on the builder name and select **Builder Name** as text field.

2.  Select on the draw amount and select **Draw Amount** as text field.

3.  Select on the loan number and select **Loan Number** as text field.

4.  All your fields should now be tagged.

![review the page](media/2ccff1073141fb9bfc02a81df5a26b96.png)

1.  Select table area of the document and select **Budget Items** table.

![select as described](media/2002f0beeb8581b84f0187d92e6feee2.png)

1.  Turn on **Advanced tagging mode**.

![select as described](media/5032e01f095a393f1c7a0585cf90a941.png)

1.  Click to and select the first cell.

![select as described](media/9202eb9aeb23fd1236e9469f026ea2ca.png)

1.  Go to the document and select the first budget category item name.

![select as described](media/d821f6dd2bc0b6f4817411e4b89bd6c7.png)

1.  The selection should automatically advance to the second cell. Select first
    budget category item amount.

![select as described](media/d55e8b6bf24c3bee162131d9c7855b71.png)

1.  The selection should automatically advance to the first cell of the second
    row. Select the second budget category item name.

![select as described](media/4eed2e3722f21dc415c6edd7dc4cb4e7.png)

1.  Continue until all the items in the table are tagged.

2.  The table should now look like the image below. Click **Done**.

![review the resulting page](media/fd2f9262d6ccd8931dea3c0635cb2431.png)

1.  Select the second document.

![select as described](media/2a66a46e088b3554695a79b7ab870bc9.png)

1.  Tag the fields and for the second document.

![select as described](media/ee124557884446b3d23227fcbe2a390c.png)

1.  Select table area of the document and select **Budget Items** table.

![select as described](media/368437d016e2dbce9e82cce7a613aff1.png)

1.  Make sure **Advanced tagging mode** is turned on.

2.  Tag all the items in the table.

3.  You should now have two documents tagged.

![select as described](media/bcdaf36954203949419d582bff9e45d6.png)

1.  Tag the rest of the documents.

2.  Click **Next**. You won’t be able to advance to the next step until you have
    finished tagging all the documents.

![select as described](media/1b71414d0d7c6cd480410ca537debeec.png)

1.  Click **Train** and wait for the training to complete.

![select as described](media/9bb2ade274d909cb482624b4d087a5cc.png)

1.  Do not navigate away from this page.

**Task \#4: Test and publish the model**

1.  The model should automatically open after the training completes or click
    **Go to models**.

2.  Click **Quick test**.

![review and test](media/eee08605ec47e8685c3a6adcc8de20c2.png)

1.  Go to the lab resources folder and open the **Test** folder.

2.  Drag the **Maria Campbell.pdf** file to the model quick test pane.

3.  The model should run and complete the document analysis.

4.  Click on the table area.

![review and test](media/288395b8eed36b4c47474a9f4b07f70e.png)

1.  You should see the budget items from the test file.

![review results](media/a9040da04ed16c1db39912e01070d866.png)

1.  Evaluate all the values the model extracted and make sure it matches the
    test document.

2.  Click **Close**.

3.  Click **Publish** and wait for the publishing to complete.

![publish](media/35c48a85d737055909dae659a297eaee.png)

1.  Your model should now be ready for use.

**Exercise \#2: Modify flow to use AI Builder model**

**Task \#1: Use AI Builder**

1.  Navigate to <https://make.powerapps.com/> and make sure you are in the Dev
    environment.

2.  Select **Solutions** and open the **Construction Funding** solution.

3.  Click **Add Existing \| AI Model**.

4.  Select your Document Processing model and click **Add**.

5.  Select **Cloud flows**, select **Process Construction Funding Request** flow
    and click **Edit**.

![select as described](media/7c247a144d176f8242baf5a9aa99b6b3.png)

1.  Click **+** insert new step after the **Get loan** step and select **Add an
    action**.

![add an action](media/c6e7189a9d5a74b4a13493c89f637fb1.png)

1.  Select the **Condition** action from the **Control** connector.

2.  Click the first operand field and select **Has Attachment** from the dynamic
    content pane.

![select as described](media/9e48ed08649b6aea0a64a11679eed642.png)

1.  Select **is equal to** for operator.

2.  Click on the second operand field, go to the dynamic content pane, and
    select the **Expression** tab.

3.  Type **true** and click **OK**.

![select as described](media/490923b617dd993d4cb9d42aa0aaa9c8.png)

1.  Rename the condition **Check if email has attachment**.

2.  Go to the **If no** branch and click **Add an action**.

3.  Select the **Send an email from a shared mailbox (V2)** action from the
    **Office 365 Outlook** connector.

4.  Click on the **Original Mailbox Address** field and select **To** in the
    dynamic content pane.

5.  Click on the **To** field and select **From** in the dynamic content pane.

6.  Enter **No attachment found** for **Subject**.

7.  Enter **Email has no attachment** in the **Body**.

8.  Rename the step **Send no attachment email**.

9.  Click **Add an action**.

![add an action to the no branch](media/8e65968477651d50e782e31867ea9759.png)

1.  Select **Terminate**.

2.  Select **Succeeded** for Status.

3.  Click **+** insert a new step and select **Add an action**.

![add an action to the no branch](media/ae5d8deb9789b4de4b0ab32804b7003a.png)

1.  Select the **Get attachment (V2)** action from the **Office 365 Outlook**
    connector.

![select as described](media/7e4b911fe3e287ac8f5d34bd3f2ef7d6.png)

1.  Click on the **Message Id** field and select **Message Id** from the dynamic
    content pane.

2.  Click on the **Attachment Id** field, go to the dynamic content pane and
    select the **Expression** tab.

3.  Paste the expression below and click **OK**.

triggerOutputs()?['body/attachments']?[0]['id']

![paste the expression](media/a1d3ccd055cfe5d09e12924a607d057a.png)

1.  Click on the **Original Mailbox Address** and select **To** from the dynamic
    content pane.

2.  Rename the step **Get email attachment**.

3.  Click on the **+** Insert a new step button below the **Get email
    attachment** step and select **Add an action**.

4.  Select the **Extract information from documents** action from the **AI
    Builder** connector.

![select extract information from form
aciton](media/3f094550d57f427eb584511d81c16c3a.png)

1.  Select the **Document Processing** you created for AI Model and select **PDF
    Document** for Form type.

2.  Click on the **Form** field and select **Content Bytes** form the dynamic
    content pane.

![select as described](media/46b68f4664a0b1d8ec0f60dbd72d8fdb.png)

1.  Click on the **+** Insert a new step button below the **Extract information
    from documents** step and select **Add an action**.

2.  Select the **Initialize variable** action from the **Variable** connector.

![select as described](media/0143d256e811b652adeff8ac0c1b1ed5.png)

1.  Enter **Work items** for Name and select **String** for Type.

2.  Rename the step **var work items** and click **+** and select **Add an
    action**.

![select and complete as described](media/e9f23c293f2e993e24957a5ce6b6f1af.png)

1.  Select the **Append to string variable** action from the **Variable**
    connector.

![select and complete as described](media/11d252a40af48d09445495ffaa63d79e.png)

1.  Select **Work items** for Name, click on the **Value** field and select
    **Budget Items Budget Category value** from the dynamic content pane.

![select and complete as described](media/3f103055f39107e08ada4137dd21d7b3.png)

1.  Notice the **Apply to each** control will be added automatically.

2.  Rename the apply to each control **Apply to each work item**.

![select and complete as described](media/972b8e644df30d5293c54bbdb6ce6792.png)

1.  Add a **comma and space** after the value in the **Append to string
    variable** action.

![select and complete as described](media/88e6a869dbd1428af8830876a220722b.png)

1.  Expand the **Create new loan draw** row step.

2.  Click on the **Amount Requested** field (remove current value if populated),
    go to the dynamic content pane, and select the **Expression** tab.

3.  Paste the expression below.

string(replace(,'\$',''))

1.  Place your cursor before the first comma and select the **Dynamic content**
    tab.

![select and complete as described](media/f3f65941d38c92c9a84486dcf9f298da.png)

1.  Select **Draw Amount value** and click **OK**.

![select and complete as described](media/709feddb520a7c371a9606b64c3a77b3.png)

1.  Select **Received** for Status Reason.

2.  Click on the **Requested On** field, got the dynamic content pane, select
    the **Expression** tab, type **utcNow(),** and click **OK**.

![select and complete as described](media/11b72679c2d5af4733dc0799a3967e49.png)

1.  Click on the **Amount Requested** value and copy. Use **[CONTROL] + [C]** to
    copy.

2.  Expand the **Calculate Risk Score** step.

3.  Remove the **drawAmount** value and paste the value you copied.

![select and complete as described](media/895123883f2b6c52eb7e305b04df95a7.png)

1.  Expand the **Run funding process** step.

2.  Remove the **RequestedAmount** value and paste the value you copied.

![select and complete as described](media/dcf73757c11d31e5b488e5f6217a432b.png)

1.  Expand the **Run inspection process** step.

2.  Remove the **Work** value and select **Work Items** from the dynamic content
    pane.

![select and complete as described](media/96bc38cf1a0d1173d6231a60b3dc6e47.png)

1.  Click **Save** and wait for the flow to be saved.

**Task \#2: Test the flow**

1.  Go to the resources folder of the lab and open the Test folder.

2.  You will attach the **Attachment AI Test** file when you send the email.

![select the file for testing](media/e9de7904b7a33d972822a3a85f0c2d5c.png)

1.  Go back to the flow and click **Test**.

2.  Select **Manually** and click **Test**.

3.  Send an email to
    [Funding@yourdomain.onmicrosoft.com](mailto:Funding@yourdomain.onmicrosoft.com)
    make sure the subject of the email is **MC3747** and you attach the
    **Attachment AI Test.pdf** file.

4.  Wait for the flow run to complete.

5.  The flow test should succeed, and you should get an email with subject line
    **Draw Approved**.

6.  Expand the **Extract Information from documents** step and review the
    **Outputs**.

![review the output](media/e6fa11b0eb253a1dde8c21aa1725cbcd.png)

1.  Expand the **Run inspection process** and review the **Work** input.

![review the output](media/57e1b24c54d37978fac3516d0e419f93.png)

1.  Review the rest of the steps and make sure the flow produced the expected
    outcome.
