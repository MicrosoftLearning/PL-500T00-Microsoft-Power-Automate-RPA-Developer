**Troubleshooting**

**Scenario**

In this lab, you will learn how to monitor and debug desktop flows.

**High-level lab objectives**

-   Monitor desktop flows

-   Debug desktop flows

-   Add retry to desktop flow

**Exercise \#1: Monitor flows**

In this exercise, you will monitor desktop flows.

**Task \#1: Monitor desktop flows**

1.  Navigate to <https://make.powerautomate.com/> and make sure you are in your
    dev environment.

2.  Click on **More** and select **Discover all**.

![Select more and discover all](media/5e8317996ac8033bd70cea66e5cd7165.png)

1.  Under **Monitor** select **Desktop flow runs**.

![Select more and discover all](media/1adebc11c9da70ab46af8d61da1dbd4a.png)

1.  If you don’t see anything, make sure you are in your Dev environment.

2.  Turn on **Auto refresh**.

![enable auto-refresh](media/eb68fabcb57f195eb615eaae1f72fe5b.png)

1.  Click on the ellipses of one the **Woodgrove Funding Manager Draw** run and
    select **See parent flow run**.

![select and complete as described](media/fd28dc20c2e904089efc9ed99ec917ab.png)

1.  You should see the parent cloud flow run (CF Manage Woodgrove Funding
    Process).

![review the screen](media/4daad9c869696ba08592a4d5c29c76dd.png)

1.  Click on the browser back button.

2.  Click to open the **Woodgrove Funding Manager Draw** run.

![select as described](media/7a6a8b388671cc32119f1955b3b218d8.png)

1.  You should see all the actions in the flow run.

![review the screen](media/dcc55a0291d94548c13cd9c78be74a62.png)

1.  Click on the start timestamp to open the **Set variable** action.

![select as described](media/4e3288ea6d25d5ea60ecfc7eb271d70c.png)

1.  Go to the **Action Details** pane and click **See output details**.

![select as described](media/bebbd8ffdc45356d81f8f7d93e3136d4.png)

1.  You should see details of the variable.

![review the details](media/9cb25f4ae5219c00615769de1efc1310.png)

1.  Close the **Outputs** pane.

2.  You may wish to review the other actions.

**Task \#2: Flow monitor**

1.  Launch **Power Automate for desktop**, make sure your dev environment is
    selected.

2.  Click **Settings**.

![select as described](media/982f61d30e17a6788e9172bfd571b8f9.png)

1.  Click on the **Monitoring/Notifications** dropdown, select **Flow monitoring
    window**, and click **Save**.

![select as described](media/a9fa9c12ea4d5ffb48ac9efc4e6cc809.png)

1.  Close the **Settings** pane.

2.  Run the **Perform Site Inspection**.

![select as described](media/7264b6872f119ea28643e98d51431cd5.png)

1.  Click **OK**.

![select as described](media/dda716c489ffe5d3a13b16e154da9c53.png)

1.  Notice the monitor. Click **Pause**.

![select as described](media/3c000846a04268bc9b17e525b0f12258.png)

1.  The flow should pause. Click **Resume**.

![select as described](media/5e49ec14c39cef8c08c0c225fb840395.png)

1.  Click **Stop**. The flow should stop, and the monitor should disappear.

**Exercise \#2: Debug flows**

**Task \#1: Debug flow**

1.  Go to Power Automate desktop flow and run the **Perform Site Inspection**
    flow again.

2.  Enter **456 Main Street** for Address and click **OK**.

![select and complete as described](media/01543e6950e233c2aa51050089ffe854.png)

1.  Wait for the flow to finish running.

2.  The flow should fail, and you should see an error in the notification.

![review the details](media/15bc31b4e1448743e2f4b47f6a21310c.png)

1.  Click **Edit** flow.

![select and complete as described](media/34acf27cc8cf7e7c478dd86d2b8b3974.png)

1.  Add a breakpoint on the first press button action. Clicking to the left of
    the line number will add a breakpoint.

![add the breakpoint](media/7afca236941e78cee137952da76b0f5e.png)

1.  Edit the property address variable and change the default value to **456
    Main Street**.

2.  Click **Run**.

3.  The flow will pause when the breakpoint is hit. Click **Run next action**.

![select run next action](media/1c61285eaee539b49044462bc0d52232.png)

1.  The flow should advance to the next action and pause again. Click **Run next
    action** again.

2.  Click **Run next action** until the flow fails.

![select and complete as described](media/ee239859a57deac83217c70c2502a2ab.png)

**Task \#2: Add retry**

1.  Click **Subflows** and select + New subflow.

![select and complete as described](media/1b907a6febdde8dea4c486546d4bca54.png)

1.  Enter **WaitFlow** for name and click **Save**.

2.  Go to the **Actions** pane, search for **wait** and double click on the
    **Wait** action.

![select and complete as described](media/2f8229bc5d24f9d2ba893508856e1998.png)

1.  Enter **60** and click **Save**.

![select and complete as described](media/14bdfcf4576ec25b2b2b7b2a0472f931.png)

1.  The subflow should now have one wait action. Select the **Main** tab.

![select and complete as described](media/131d77ab2026e4fb520438a0d3ba5143.png)

1.  Go to the **Actions** pane, search for **error**, drag **On block error**
    action, and place it after the **Get details of element on web page** for
    the **JobNumber** action.

![select and complete as described](media/7818d7c97e433ad759a7ced7a0e82855.png)

1.  Enter **RetryOnError** for Name, click **+ New rule**, and select **Run
    subflow**.

![select and complete as described](media/6818fb875b17deec40cf47a440d78769.png)

1.  Select the **WaitFlow** you created and click **Continue flow run**.

![select and complete as described](media/ea75a2bb840bc33790888340bc9236ac.png)

1.  Select **Go to beginning of block** for Exception handling mode and click
    **Save**.

![select and complete as described](media/5bd61421a1d2ef412c80fdc257690c84.png)

1.  Click to select the action below the error block.

![select and complete as described](media/54ea14565ad1d7d8f235856f21246c73.png)

1.  Hold the **[SHIFT]** and click to select the **End** loop action.

![select and complete as described](media/92591580fba8345234ddc396bfd2b32b.png)

1.  Drag all the selected actions and drop them inside the error block.

2.  The **On block error** action should now look like the image below.

![review the screen](media/f73e32dcd98503fe8e79a9295626970c.png)

1.  Click **Save** and wait for the flow to be saved.

**Task \#3: Test**

1.  Remove the breakpoint and Click **Run**.

2.  The flow will switch to the subflow if error occurs.

![watch the flow run](media/003a17ab8c06a5e905f7737e54d11146.png)

1.  The flow will go back to the main flow after **60** seconds.

2.  The process should complete successfully.

![review completed flow run](media/d48585e4861de21295c1122558994487.png)
