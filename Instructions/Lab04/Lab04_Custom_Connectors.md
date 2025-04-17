---
lab:
    title: 'Lab 4 - Custom Connectors'
    module: 'Module 4 - Custom Connectors'
---

# Custom Connectors

## Scenario

In this lab, you will build a custom connector for A Datum’s Risk Score API.

## High-level lab objectives

-   Build a custom connector

-   Modify the cloud flow to use the connector

## Exercise 1: Create a custom connector

### Task 1: Create a new solution

1.  Navigate to `https://make.powerapps.com/` and make sure you are in the Dev
    environment.

2.  Select **Solutions** and click **+ New solution**. We are creating a new
    solution to keep the custom connector separate from the flow that uses it
    which is the current requirement of using a custom connector.

3.  Enter `Builder Risk Service` for Display name, select **Relecloud** for
    Publisher, and click **Create**.

    ![create your new solution as described](media/fa0ae4cd4ebbb8e39f3d38577afc9584.png)

### Task 2: Create custom connector

1.  Click **+ New** and select **Automation \| Custom connector**.

    ![add a new custom connector](media/3f5ddeb21f6f7f1c71d8c7a9927230fc.png)

1.  Enter `Builder Risk Service` for Connector Name.

    ![name the connector](media/517c5a289ad72b474d2f2b06a4e87f70.png)

1.  Enter `Service for evaluating builder risk` for Description, enter
    `adatumbuilderrisktest.azurewebsites.net` for Host, and click **Create
    connector**.

    ![create the connector](media/a62b7f8add7df202bf0ec9fb50fe84f3.png)

### Task 3: Import Open API

1.  Navigate to `https://adatumbuilderrisktest.azurewebsites.net/`

1.  Click **Download Logo** and save the logo on your machine.

1.  Click on the **API Key** link.

    ![download API key](media/e8a5896b9d940bf33fdb549301078f79.png)

1.  Copy the **API Key** and save it on a notepad.

1.  Click **Return to home**.

1.  Click on the **API documentation** link.

1.  Review the documentation.

1.  Close the documentation browser tab or window, after you finish reviewing.

1.  Click on the **Open API definition file** link.

    ![click to review definition](media/532e87a83a468799e07f3e6fd163aa42.png)

1.  On your keyboard press **CTRL + S** and select **Save**. Now the file is
    saved on your machine.

1.  Navigate to `https://make.powerautomate.com/` and make sure you are in the
    Dev environment.

1.  Click **More** and select **Discover all**.

    ![Expand more option in navifation](media/2682339c99470af24e9711377e8ae641.png)

1.  Scroll down and select **Custom connectors** under data.

    ![Find custom connectors](media/03e4103cb11aad692ebe222d2ebde51f.png)

1.  Click on the **…** more actions button of the **Builder Risk Service**
    custom connector and select **Update from OpenAPI file**.

    ![locate and update the OpenAPI file](media/b58deb8548a5758fa5b3f08c4ca900e0.png)

1.  Click **Import**.

1.  Select the **swagger.json** file you saved to your machine and click
    **Open**.

1.  Click **Continue**.

    ![Import the file](media/059002b176dfb4c8d867f016822e449e.png)

1.  Click **Upload** under the logo.

1.  Select the logo you downloaded and click **Open**.

1.  Enter `Service for evaluating builder risk` for Description, enter

    `adatumbuilderrisktest.azurewebsites.net` for Host, and select **Security**
    from the breadcrumb navigation bar at the top of the screen.

    ![enter details as described](media/1106c5673216d09af787c713b880d0b0.png)

1.  Select **Definition** from the breadcrumb navigation bar at the top of the
    screen and see the operation imported.

1.  Turn on **Swagger Editor**.

    ![toggle swagger editor](media/8f9d496c2104be8aed2e97c02b4263b9.png)

1.  Have a look at the Swagger Editor and then turn off the **Swagger Editor**.

1.  Select **Update connector** and wait for the connector to be updated.

1.  Do not navigate away from this page.

### Task 4: Test connector

1.  Select **Test** from the breadcrumb navigation bar at the top of the screen
    and click **+ New connection**.

    ![select new connection](media/f3b0405024d744449d62a0a03d7d90ce.png)

1.  Paste your **API Key** and click **Create connection**.

1.  Click the **Refresh connections** button, on the right. The connection you
    just created should be the **Selected connection**.

1.  Under CalcRiskScore, enter `Contoso` for builderName, `7165 Brock Lane
    Renton, WA 61795 U.S.` for propertyAddress, `JG7165` for loanNumber,
    `645000` for loanAmount, `500000` for creditAvailable, `100000` for
    drawAmount, and click **Test operation**.

    ![Enter details as described](media/9837ea1ae2abfeb49cb5f5db0aa0f7d9.png)

1.  The test should run successfully, and you should receive a score and a
    reason.

    ![review results](media/7486f316bb779aae565e8954f7b29f20.png)

1.  Click **Close** to return to the list of Custom connectors.

## Exercise 2: Modify cloud flow to use connector

### Task 1: Use custom connector in flow

1.  Navigate to `https://make.powerapps.com/` and make sure you are in the Dev
    environment.

1.  Select **Solutions** and open the **Construction Funding** solution.

1.  Select **Cloud flows**, select **Process Construction Funding Request** flow
    and click **Edit**.

    ![locate and edit the flow](media/7c247a144d176f8242baf5a9aa99b6b3.png)

1.  Click **+** insert new step after the **Check if loan number found**
    condition and select **Add an action.**

    ![add a new step](media/2b758feb449d7e1398a07ed9d8be7f02.png)

1.  Select **Get a row by ID** Microsoft Dataverse.

    ![select get a row by ID action](media/cb82c798239df5d92cc747b7e82750f6.png)

1.  Select **Loans** for Table name, click on the **Row ID** field and select
    **LoanID** from the dynamic content pane.

    ![enter details as described](media/fcac4232df3967fd2a64a79ac3f3ed49.png)

1.  Rename the step **Get loan**.

1.  Go to the **+** Insert a new step button after the **Run inspection
    process** and select **Add an action**.

    ![add an action](media/f66f6fccb86e43b977f2908a20eb3868.png)

1.  Go to the **Custom** tab and select **Builder Risk Service**.

    ![add the custom action you
provided](media/57477ad2de26ea5c48a791af16abbb63.png)

1.  Select the **Calculate Risk Score** action.

1.  Enter `Risk Service` for Connection name, paste the API Key you copied
    earlier, and click **Create**.

    ![enter details as described](media/8b200aa53e536ab933713e78250c284d.png)

1.  Click on the **builderName** field and select **Builder** from the dynamic
    content pane.

    ![enter details as described](media/b0b78928b988dd90991c30c934723708.png)

1.  Click on the **propertyAddress** field and select **Address** from the
    dynamic content pane.

1.  Click on the **loanNumber** field and select **Loan Number** from the
    dynamic content pane.

1.  Click on the **loanDate** field and select **Loan Date** from the dynamic
    content pane.

1.  Click on the **loanAmount** field and select **Loan Amount** form the
    dynamic content pane.

1.  Click on the **creditAvailable** field and select **Credit Available** from
    the dynamic content pane.

1.  Enter `80000` for drawAmount.

1.  The calculate risk score step should now look like the image below.

    ![review the details](media/0034266a505c98138d7ea483044f65cb.png)

1.  Click on the **+** Insert a new step after the **Calculate Risk Score** step
    and select **Add an action**.

    ![add an action](media/69fd4cca2cf7d68e2ca3c980f03e1e16.png)

1.  Select **Update a row** Microsoft Dataverse.

1.  Select **Loan Draws** for Table name, click on the **Row ID** field and
    select **Loan Draw** from the dynamic content pane.

1.  Expand Show advanced options and Click on the **Risk Score** field and
    select **score** from the dynamic content pane.

1.  Select **Risk Scored** for Status reason.

1.  Rename the step **Update loan draw risk score**.

1.  The update loan draw step should look like the image below.

    ![review the details](media/2cd5ba4b44cc03d954977c40a206ec59.png)

1.  Click to expand the **Run inspection process** step.

1.  Remove the **PropertyAddress** value and select **Address** from the dynamic
    content pane.

    ![enter details as described](media/0b9bb02183ca865194ac2433c36f7f87.png)

1.  Expand the **Run funding process** step.

1.  Remove the **RiskScore** value and select **Score** from the dynamic content
    pane.

    ![enter details as described](media/81a080539114467e0f1224094f5328d5.png)

1.  Click **Save** and wait for the flow to be saved.

### Task 2: Test the flow

1.  Click **Test**.

1.  Select **Manually** and click **Test**.

1.  Send an email to
    [Funding@yourdomain.onmicrosoft.com](mailto:Funding@yourdomain.onmicrosoft.com)
    with the Subject line as **PS7765**.

1.  The flow test should run and succeed.

1.  On the **Run History** for the flow test, all steps should show a green
    tick. Expand the **Calculate Risk Score** step.

1.  The output should look like the image below:

    ![test the flow](media/44d8de7e2779c95e2546babf01f95a64.png)

1.  You should receive an email with the subject **Draw Approved**.
