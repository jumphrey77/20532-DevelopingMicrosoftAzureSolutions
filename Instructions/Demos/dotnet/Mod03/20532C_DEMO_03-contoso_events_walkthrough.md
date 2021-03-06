# Module 3: Hosting Web Applications on the Azure Platform

# Demo: Contoso Events Walkthrough

1.  On the Start screen, click the **Desktop** tile.

1.  On the taskbar, click the **File Explorer** icon.

1.  In the Libraries window, go to Allfiles **(F):\\Mod03\\Democode\\Contoso.Events**, and then double-click **Contoso.Events.sln**.

1.  In the **Solution Explorer** pane, expand **Shared**.

1.  In the **Solution Explorer** pane, expand the **Contoso.Events.Data.Generation** project.

1. On the Start screen, click the **Internet Explorer** tile.

2. Go to https://portal.azure.com

3. Enter the email address of your Microsoft account. Click **Continue**.

4. Enter the password for your Microsoft account.

5. Click **Sign In**.

1.  In the navigation pane on the left side of the Azure Portal, scroll down, and then click **More Services**.

2. In the **Browse** blade that displays, click **Storage accounts**.

3. In the **Storage accounts** blade that displays, view your list of storage account instances.

4. At the top of the **Storage accounts** blade, click the **Add** button.

5. In the **Create storage account** blade that displays, perform the following steps:

    a. In the **Name** box, provide a globally unique value.

    b. In the **Deployment model** section, ensure that the *Resource manager* option is selected.

    c. In the **Account kind** list, ensure that the *General purpose* option is selected.

    d. In the **Performance** section, ensure that the *Standard* option is selected.

    e. Click on the **Replication** list and select the **Locally-Redundant Storage (LRS)** option.

    f. In the **Location** list, select the region closest to your current location.

    g. In the **Resource group** section, select the **Use existing** option.

    h. In the **Resource group** section, locate the dialog box and provide the value **20532**.

    i. Ensure that the **Pin to dashboard** option is selected.

    j. Click **Create**.

6. Once the **Storage account** instance is created, the blade for the new instance will open automatically.

7. In the **Storage account** blade, record the name of your *storage account*.

8. In the **Settings** section, select the **Access keys** option.

9. In the **Access keys** blade, locate a key that you wish to use.

    > **Note:** you can use any of the keys listed for this lab.

10. For the access key you selected, click the three ellipsis (...) button to the right of the key. Once clicked, select the **View connection string** option.

10. In the **View connection string** dialog, record your connection string for the access key you selected.

    > **Note:** This connection string will be used in various parts of this lab.

11. Close the **View connection string** dialog.

1.  Switch back to the **Contoso.Events – Microsoft Visual Studio** window.

1.  In the **Solution Explorer** pane, right-click the **Contoso.Events.Data.Generation** project, point to **Debug**, and then click **Start New Instance**.

1. Wait for the console application to close and also for debugging to stop.

1. Close the Contoso.Events – Microsoft Visual Studio application.

1. On the Start Screen, right-click the **Visual Studio 2015** tile, and then click **Run as Administrator**.

1. On the **File** menu, point to **Open**, and then click **Project/Solution**.

1. In the **Open Project** dialog box, perform the following steps:

	a.  Go to **Allfiles (F):\\Mod03\\Democode\\Contoso.Events**.

	b.  Click the **Contoso.Events** solution file.

	c.  Click **Open**.

1. In the **Solution Explorer** pane, expand the **Shared** solution folder.

2. In the **Solution Explorer** pane, expand the **Contoso.Events.Data.Generation** project.

3. Locate and open the **app.config** file in the project.

4. Within the **app.config** file, locate the following configuration setting:

    ```
    <add key="StorageConnectionString" value="UseDevelopmentStorage=true" />
    ```

5. Update the setting by replacing the value of the **value** attribute (currently *UseDevelopmentStorage=true*) with your *Storage Account*'s connection string.

3. In the **Solution Explorer** pane, right-click the **Contoso.Events.Data.Generation** project, point to **Debug**, and then click **Start New Instance**.

4. Wait for debugging to complete (when the console window closes).

#### Task 3: Download generated sign-in sheets from the blob storage

1. In the **Solution Explorer** pane, right-click the **Contoso.Events** solution, and then click **Properties**.

1. Navigate to the **Startup Project** section located under the **Common Properties** header.

1. In the **Startup Project** section, locate and select the **Multiple startup projects** option.

1. Within the **Multiple startup projects** table, perform the following actions:

    a. Locate the **Contoso.Events.Web** entry and change it's *Action* from **None** to **Start**.

    b. Locate the **Contoso.Events.Management.Old** entry and change it's *Action* from **None** to **Start**.

    c. Locate the **Contoso.Events.Worker** entry and change it's *Action* from **None** to **Start**.

1. Click the **OK** button to close the *Property* dialog.

1. In the **Solution Explorer** pane, expand the **Administration** solution folder.

2. In the **Solution Explorer** pane, expand the **Contoso.Events.Management.Old** project.

3. Locate and open the **web.config** file in the project.

4. Within the **web.config** file, locate the following configuration setting:

    ```
    <add key="Microsoft.WindowsAzure.Storage.ConnectionString" value="UseDevelopmentStorage=true" />
    ```

5. Update the setting by replacing the value of the **value** attribute (currently *UseDevelopmentStorage=true*) with your *Storage Account*'s connection string.

1. In the **Solution Explorer** pane, expand the **Roles** solution folder.

2. In the **Solution Explorer** pane, expand the **Contoso.Events.Web** project.

3. Locate and open the **web.config** file in the project.

4. Within the **web.config** file, locate the following configuration setting:

    ```
    <add key="Microsoft.WindowsAzure.Storage.ConnectionString" value="UseDevelopmentStorage=true" />
    ```

5. Update the setting by replacing the value of the **value** attribute (currently *UseDevelopmentStorage=true*) with your *Storage Account*'s connection string.

2.  In the **Solution Explorer** pane, expand the **Contoso.Events.Worker** project.

3. Locate and open the **app.config** file in the project.

4. Within the **app.config** file, locate the following configuration setting:

    ```
    <add name="AzureWebJobsStorage" connectionString="UseDevelopmentStorage=true" />
    ```

5. Update the setting by replacing the value of the **connectionString** attribute (currently *UseDevelopmentStorage=true*) with your *Storage Account*'s connection string.

4. Within the **app.config** file, locate the following configuration setting:

    ```
    <add name="AzureWebJobsDashboard" connectionString="UseDevelopmentStorage=true" />
    ```

5. Update the setting by replacing the value of the **connectionString** attribute (currently *UseDevelopmentStorage=true*) with your *Storage Account*'s connection string.

4. Within the **app.config** file, locate the following configuration setting:

    ```
    <add key="StorageConnectionString" value="UseDevelopmentStorage=true" />
    ```

5. Update the setting by replacing the value of the **value** attribute (currently *UseDevelopmentStorage=true*) with your *Storage Account*'s connection string.

1.  On the **Debug** menu, click **Start Debugging**.

1.  In Internet Explorer, locate and click the **Home – Contoso Events** window.

1.  Click any one of the sales conference events to go to the event details webpage.

	> If a sales conference is not listed in the Upcoming Events section, you can click **All Events** to see all the events.

1.  To go to the event’s registration page, click **Register Now**.

1.  In the **Region** box, type **Western**.

1.  In the **AnnualSales** box, provide the value **45000**.

1.  In the **FirstName** box, provide the value **Corrine**.

1.  In the **LastName** box, provide the value **Horn**.

1.  Click **Submit**.

1.  In Internet Explorer, locate and click the **Home – Contoso Events Administration** window.

1.  Click **Go to Events List**.

1.  Locate the same sales conference that you registered for in the previous step.

1. In the grid, click **Sign-In Sheet** next to the event’s name.

1. Every 30 seconds (or less), refresh the page to see if the Sign-in Sheet is generated.

	> When the box changes from blue to yellow and a hyperlink with the text Sign-In Sheet displays, it indicates that the Sign-in Sheet is generated.

1.  Click the **Sign-In Sheet** hyperlink to download the Microsoft Word document.

1.  To view the file, click **Open** in the download dialog box.

1.  Close the **Internet Explorer** application.

1.  Close the **Contoso.Events – Microsoft Visual Studio** application.
