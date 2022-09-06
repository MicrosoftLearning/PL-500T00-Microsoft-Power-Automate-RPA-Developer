---
title: Lab 5 - Integrate AI
---

# Scenario

In this lab, you will be using AI Builder to process the construction
funding request form document that was emailed to the funding shared
mailbox to extract essential information. The extracted information will
be stored in Dataverse for use in the funding process.

# High-level lab steps

-   Use sample request forms to train an AI Builder model

-   Modify the cloud flow to use the model to process the inbound
    document

-   Store the extracted information in the Loan Draw table

# Exercise \#1: Train model for request form

In this exercise, you will create an AI Builder model that will process
the funding request form.

## Task \#1: Create AI Builder model

1.  Go to the lab resources folder and open the **Train** folder.

2.  Click to open **Jim Glynn.pdf**.

> <img src="../L05/media/image1.png" style="width:6.21051in;height:1.92221in"
> alt="select the pdf in file explorer" />

3.  The documents from which the model will extract the data will look
    like this document. Keep this file open, you will need it during
    model creation.

> <img src="../L05/media/image2.png" style="width:5.37469in;height:3.23572in"
> alt="review the document" />

4.  Navigate to <https://make.powerapps.com/> and make sure you are in
    the Dev environment.

5.  Expand **AI Builder** and select **Models**.

> <img src="../L05/media/image3.png" style="width:1.8773in;height:1.69415in"
> alt="select AI Builder models" />

6.  Click Start free trial.

7.  Click **+ Build a model**.

8.  Select **Extract custom information from document**.

> <img src="../L05/media/image4.png" style="width:5.04074in;height:2.34098in"
> alt="Choose document processing" />

9.  Click **Get started**.

10. Select **Structured and semi-structured documents** and click
    **Next**.

> <img src="../L05/media/image5.png" style="width:5.85245in;height:2.13777in"
> alt="select as described" />

11. Do not navigate away from this page.

12. Go to the **Jim Glynn** pdf fie, you will create fields and a table
    in the model that match the fields and the table in this document.

> <img src="../L05/media/image6.png" style="width:5.25333in;height:3.38548in"
> alt="select as described" />

13. Go back to the model. Click the chevron button on the **+ Add**
    button and select **Field**.

> <img src="../L05/media/image7.png" style="width:5.89728in;height:1.93804in"
> alt="select as described" />

14. Enter **Owner Name** and click **Done**.

> <img src="../L05/media/image8.png" style="width:3.56616in;height:2.20454in"
> alt="enter details as described" />

15. Click the chevron button on the **+ Add** button and select
    **Field** again.

16. Enter **Property Address** and click **Done**.

17. Click the chevron button on the **+ Add** button and select
    **Field**.

18. Enter **Builder Name** and click **Done**.

19. Click the chevron button on the **+ Add** button and select
    **Field**.

20. Enter **Draw Amount** and click **Done**.

21. Click the chevron button on the **+ Add** button and select
    **Field** one more time.

22. Enter **Loan Number** and click **Done**.

23. You should now have five fields added.

> <img src="../L05/media/image9.png" style="width:5.40839in;height:3.09711in"
> alt="review the resulting screen" />

24. You will now add the table details. Click the chevron button on the
    **+ Add** button and select **Single page table**.

> <img src="../L05/media/image10.png" style="width:5.47537in;height:2.27614in"
> alt="select as described" />

25. Enter **Budget Items** for Table name.

26. Click on **Column 1** and select **Rename column**.

> <img src="../L05/media/image11.png" style="width:4.02554in;height:1.65193in"
> alt="select as described" />

27. Enter **Budget Category** and click **Rename**.

> <img src="../L05/media/image12.png" style="width:4.11431in;height:1.90902in"
> alt="enter details as described" />

28. Click **+** **New column**.

> <img src="../L05/media/image13.png" style="width:4.72788in;height:1.15066in"
> alt="select as described" />

29. Enter **Amount** and click **Add**.

30. Your table should now have 2 columns. Click **Done**.

> <img src="../L05/media/image14.png" style="width:4.83007in;height:2.8067in"
> alt="review the results" />

31. Click **Next**.

32. Do not navigate away from this page.

## Task \#2: Add sample documents

1.  Click **New collection.**

> <img src="../L05/media/image15.png" style="width:5.5557in;height:1.8519in"
> alt="select as described" />

2.  Enter **Sample documents** for collection name and click **+** add.

> <img src="../L05/media/image16.png" style="width:2.53767in;height:1.95586in"
> alt="select as described" />

3.  Click **Add documents**.

4.  Select **My device**.

5.  Select all **5** PDF files located in the **Train** folder and click
    **Open**.

> <img src="../L05/media/image17.png" style="width:4.53623in;height:1.77281in"
> alt="select the files" />

6.  Click **Upload 5 documents** and wait for the files to be loaded.

7.  Click **Close**.

> <img src="../L05/media/image18.png" style="width:4.78016in;height:3.50392in"
> alt="confirm the selection" />

8.  Click **Next**.

9.  Do not navigate away from this page.

## Task \#3: Tag documents

1.  Click on the name of the owner and select **Owner Name** as field.

> <img src="../L05/media/image19.png" style="width:5.38996in;height:1.89858in"
> alt="select as described" />

2.  Select on the address and select **Property Address** as field.

> <img src="../L05/media/image20.png" style="width:5.57969in;height:1.92547in"
> alt="select as described" />

3.  Select on the builder name and select **Builder Name** as field.

4.  Select on the draw amount and select **Draw Amount** as field.

5.  Select on the loan number and select **Loan Number** as field.

6.  All your fields should now be tagged.

> <img src="../L05/media/image21.png" style="width:4.96767in;height:1.97539in"
> alt="review the page" />

7.  Select table area of the document and select **Budget Items** table.

> <img src="../L05/media/image22.png" style="width:5.4132in;height:2.65108in"
> alt="select as described" />

8.  Turn on **Advanced tagging mode**.

> <img src="../L05/media/image23.png" style="width:5.8628in;height:1.39353in"
> alt="select as described" />

9.  Click to select the first cell.

> <img src="../L05/media/image24.png" style="width:5.05462in;height:2.15163in"
> alt="select as described" />

10. Go to the document and select the first budget category item name.

> <img src="../L05/media/image25.png" style="width:5.94137in;height:0.96547in"
> alt="select as described" />

11. The selection should automatically advance to the second cell.
    Select first budget category item amount.

> <img src="../L05/media/image26.png" style="width:6.24922in;height:1.49981in"
> alt="select as described" />

12. The selection should automatically advance to the first cell of the
    second row. Select the second budget category item name.

> <img src="../L05/media/image27.png" style="width:5.93676in;height:1.38524in"
> alt="select as described" />

13. Continue until all the items in the table are tagged.

14. The table should now look like the image below. Click **Done**.

> <img src="../L05/media/image28.png" style="width:5.93611in;height:3.06382in"
> alt="review the resulting page" />

15. Select the second document.

> <img src="../L05/media/image29.png" style="width:4.9767in;height:2.16563in"
> alt="select as described" />

16. Tag the fields and for the second document.

> <img src="../L05/media/image30.png" style="width:5.62225in;height:1.85126in"
> alt="select as described" />

17. Select table area of the document and select **Budget Items** table.

> <img src="../L05/media/image31.png" style="width:5.73933in;height:2.47355in"
> alt="select as described" />

18. Make sure **Advanced tagging mode** is turned on.

19. Tag all the items in the table.

20. You should now have two documents tagged.

> <img src="../L05/media/image32.png" style="width:4.04329in;height:4.08393in"
> alt="select as described" />

21. Tag the rest of the documents.

22. Click **Next**. You won’t be able to advance to the next step until
    you have finished tagging all the documents.

> <img src="../L05/media/image33.png" style="width:5.34603in;height:2.23779in"
> alt="select as described" />

23. Click **Train** and wait for the training to complete.

> <img src="../L05/media/image34.png" style="width:4.37941in;height:2.36657in"
> alt="select as described" />

24. Do not navigate away from this page.

## Task \#4: Test and publish the model

1.  The model should automatically open after the training completes.

2.  Click **Quick test**.

> <img src="../L05/media/image35.png" style="width:5.51187in;height:1.67947in"
> alt="review and test" />

3.  Go to the lab resources folder and open the **Test** folder.

4.  Drag the **Maria Campbell.pdf** file to the model quick test pane.

5.  The model should run and complete the document analysis.

6.  Click on the table area.

> <img src="../L05/media/image36.png" style="width:3.82541in;height:2.24413in"
> alt="review and test" />

7.  You should see the budget items from the test file.

> <img src="../L05/media/image37.png" style="width:5.07516in;height:2.54138in"
> alt="review results" />

8.  Evaluate all the values the model extracted and make sure it matches
    the test document.

9.  Click **Close**.

10. Click **Publish** and wait for the publishing to complete.

> <img src="../L05/media/image38.png" style="width:5.53771in;height:3.20016in"
> alt="publish" />

11. Your model should now be ready for use.

# Exercise \#2: Modify flow to use AI Builder model

## Task \#1: Use AI Builder

1.  Navigate to <https://make.powerapps.com/> and make sure you are in
    the Dev environment.

2.  Select **Solutions** and open the **Construction Funding** solution.

3.  Click **Add Existing | AI Model**

4.  Select your Document Processing model and click **Add**.

5.  Select **Cloud flows**, select **Process Construction Funding
    Request** flow and click **Edit**.

> <img src="../L05/media/image39.png" style="width:5.49167in;height:1.90096in"
> alt="select as described" />

6.  Click **+** insert new step after the **Get loan** step and select
    **Add an action**.

> <img src="../L05/media/image40.png" style="width:5.82201in;height:1.78061in"
> alt="add an action" />

7.  Select **Condition**.

8.  Click the first operand field and select **Has Attachment** from the
    dynamic content pane.

> <img src="../L05/media/image41.png" style="width:4.81115in;height:2.19792in"
> alt="select as described" />

9.  Select **is equal to** for operator.

10. Click on the second operand field, go to the dynamic content pane,
    and select the **Expression** tab.

11. Type **true** and click **OK**.

> <img src="../L05/media/image42.png" style="width:5.16836in;height:1.87961in"
> alt="select as described" />

12. Rename the condition **Check if email has attachment**.

13. Go to the **If no** branch and click **Add an action**.

14. Select **Send an email from a shared mailbox (V2).**

15. Click on the **Original Mailbox Address** field and select **To** in
    the dynamic content pane.

16. Click on the **To** field and select **From** in the dynamic content
    pane.

17. Enter **No attachment found** for **Subject**.

18. Enter **Email has no attachment** in the **Body**.

19. Rename the step **Send no attachment email**.

20. Click **Add an action**.

> <img src="../L05/media/image43.png" style="width:5.0462in;height:3.83587in"
> alt="add an action to the no branch" />

21. Select **Terminate**.

22. Select **Success** for Status.

23. Click **+** insert a new step and select **Add an action**.

> <img src="../L05/media/image44.png" style="width:5.82458in;height:2.14564in"
> alt="add an action to the no branch" />

24. Select **Get attachment (V2).**

> <img src="../L05/media/image45.png" style="width:4.52188in;height:2.56477in"
> alt="select as described" />

25. Click on the **Message Id** field and select **Message Id** from the
    dynamic content pane.

26. Click on the **Attachment Id** field, go to the dynamic content pane
    and select the **Expression** tab.

27. Paste the expression below and click **OK**.

triggerOutputs()?['body/attachments']?[0]['id']

> <img src="../L05/media/image46.png" style="width:5.19345in;height:1.95698in"
> alt="paste the expression" />

28. Click on the **Original Mailbox Address** and select **To** from the
    dynamic content pane.

29. Rename the step **Get email attachment**.

30. Click on the **+** Insert a new step button below the **Get email
    attachment** step and select **Add an action**.

31. Select **Extract information from forms**.

> <img src="../L05/media/image47.png" style="width:4.45924in;height:2.29632in"
> alt="select extract information from form aciton" />

32. Select the **Document Processing** you created for AI Model and
    select **PDF Document** for Form type.

33. Click on the **Form** field and select **Content Bytes** form the
    dynamic content pane.

> <img src="../L05/media/image48.png" style="width:5.39587in;height:2.27365in"
> alt="select as described" />

34. Click on the **+** Insert a new step button below the **Extract
    information from forms** step and select **Add an action**.

35. Select **Initialize variable**.

> <img src="../L05/media/image49.png" style="width:5.09722in;height:2.51623in"
> alt="select as described" />

36. Enter **Work items** for Name and select **String** for Type.

37. Rename the step var **work items** and click **+** and select **Add an action**.

> <img src="../L05/media/image50.png" style="width:4.67138in;height:2.37681in"
> alt="select and complete as described" />

38. Select **Append to string variable**.

> <img src="../L05/media/image51.png" style="width:5.12782in;height:2.61455in"
> alt="select and complete as described" />

39. Select **Work Items** for Name, click on the **Value** field and
    select **Budget Items Budget Category value** from the dynamic
    content pane.

> <img src="../L05/media/image52.png" style="width:5.51966in;height:2.28217in"
> alt="select and complete as described" />

40. Apply to each control will be added automatically.

41. Rename the apply to each control **Apply to each work item**.

> <img src="../L05/media/image53.png" style="width:4.35486in;height:3.74403in"
> alt="select and complete as described" />

42. Add comma and space in front of the value.

> <img src="../L05/media/image54.png" style="width:4.89526in;height:2.45193in"
> alt="select and complete as described" />

43. Expand the **Create new loan draw** row step.

44. Click on the **Amount Requested** field, go to the dynamic content
    pane, and select the **Expression** tab.

45. Paste the expression below.

string(replace(,'$',''))

46. Place your cursor before the first comma and select the **Dynamic
    content** tab.

> <img src="../L05/media/image55.png" style="width:5.21222in;height:2.34717in"
> alt="select and complete as described" />

47. Select **Draw Amount value** and click **OK**.

> <img src="../L05/media/image56.png" style="width:5.26821in;height:2.41178in"
> alt="select and complete as described" />

48. Select **Received** for Status Reason.

49. Click on the **Requested On** field, got the dynamic content pane,
    select the **Expression** tab, type **utcNow(),** and click **OK**.

> <img src="../L05/media/image57.png" style="width:5.63131in;height:1.77061in"
> alt="select and complete as described" />

50. Click on the **Requested Amount** value and copy. Use
    **\[CONTROL\] + \[C\]** to copy.

51. Expand the **Calculate Risk Score** step.

52. Remove the **drawAmount** value and paste the value you copied.

> <img src="../L05/media/image58.png" style="width:4.56684in;height:2.61402in"
> alt="select and complete as described" />

53. Expand the **Run funding process** step.

54. Remove the **RequestedAmount** value and paste the value you copied.

> <img src="../L05/media/image59.png" style="width:4.23974in;height:2.1819in"
> alt="select and complete as described" />

55. Expand the **Run inspection process** step.

56. Remove the **Work** value and select **Work Items** from the dynamic
    content pane.

> <img src="../L05/media/image60.png" style="width:4.00462in;height:2.15719in"
> alt="select and complete as described" />

57. Click **Save** and wait for the flow to be saved.

## Task \#2: Test the flow

1.  Go to the resources folder of the lab and open the Test folder.

2.  You will attach the **Attachment AI Test** file when you send the
    email.

> <img src="../L05/media/image61.png" style="width:5.52944in;height:1.00782in"
> alt="select the file for testing" />

3.  Go back to the flow and click **Test**.

4.  Select **Manually** and click **Test**.

5.  Send an email to <Funding@yourdomain.onmicrosoft.com> make sure the
    subject of the email is **MC3747** and you attach the **Attachment
    AI Test.pdf** file.

6.  Wait for the flow run to complete.

7.  Flow test should succeed, and you should get an email with Subject
    Funding Approved.

8.  Expand the **Extract Information from forms** step and review the
    **Outputs**.

> <img src="../L05/media/image62.png" style="width:3.68729in;height:4.88898in"
> alt="review the output" />

58. Expand the **Run inspection process** and review the **Work** input.

> <img src="../L05/media/image63.png" style="width:3.50885in;height:2.4807in"
> alt="review the output" />

59. Review the rest of the steps and make sure the flow produced the
    expected outcome.
