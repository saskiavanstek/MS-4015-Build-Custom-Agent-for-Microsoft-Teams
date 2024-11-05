---
lab:
    title: 'Create a Custom Agent'
---
<!--
Edit the metadata above to manage the list of exercises in the home page of the GitHub site that gets generated.
You can delete the module and edit index.md in the root of the repo to customize the display so that only the exercises are listed
To enable GitHub page publishing, edit the Page settings for the repo and publish from the main branch
-->

# Exercise title <Create Azure OpenAI resource>

In this exercise you will create an Azure OpenAI resource that serves as the foundation for creating your custom agent.

This exercise should take approximately **XX** minutes to complete. <!-- update with estimated duration -->

## Task <!-- Create Azure OpenAI resource -->

First, you need to ...

1. Navigate to **https://portal.azure.com** in your edge browser.
1. Sign into the aure portal using the credential provided to you in this lab environment.
1. In the search box type in **azure openai** and press enter.
1. A result called **Azure OpenAI** should appear as an option. At the bottom left hand corner of this option is a button labled **Create**. Press the **Create** button.
1. Under the page **Create Azure OpenAI** set the following fields:
   
   a. **Subscription** leave as the default value.
   
   b. **Resource Group** : Press the dropdown and select the Resource Group option that already exists.
   
   c. **Name** : Type in any name you choose.
   
   d. **Pricing tier**: Select the default value **Standard S0**.
   
Select **Next**.

6. Under the next page, in the **Network** tab, Select the option **All networks, including the internet, can access this resource.**
Select **Next**.
7. Under the next pagein the **Tags** tab, leave the Name and Value fields blank.
Select **Next**.
8. Under the next page, in the **Review + submit** tab, press **Create**.
9. You will be taken to a page where this newly created Azure OpenAI resource is being created. You will see the words **Deployment in progress**. Wait for a few second for this resource to finish deploying. Once the resource is deployed, click on the button **Go to Resource**.
10. **Result:** You will now be in the page with newly created Azure OpenAI resource. You can verify by checking the name of the resource in the top left hand corner of the page. This name should match the name you chose for step 5c above.


## Deploy a Chat model

Now let's, ...

1. In the page for your newley created Azure OpenAI resource, click **Go to Azure OpenAI Studio** in the ribbon at the top of the page.
2. In the new page titled **Welcome to Azure OpenAI service**, click on **Chat** on the navigation menu to the left of the screen.
3. In the new page titled **Chat playground**, under **Setup**, select **+ Create new deployment** > **From base models**.
4. In the pop up window titled **Select a chat completion model** scroll down and select the option **gpt-4o** > **Confirm**.
5. In the **Deploy model gtp-4o** window, leave everything in it's default setting and select **Deploy**.
6. In the **Chat playground** page, select **Add your data** located near the bottom of the screen > **+ Add a data source**.
7. In the **Select or add data source** window, select  the dropdown for **Select data source** and select **Upload files (preview)**.
8. In the next page for **Data source**, ensure the dropdown for **Select data source** is set to **Upload files (preview)**
   
   a. In the **Subscription** field, ensure the default value is selected.
   
    b. In the **Select Azure Blob storage resource** field, select **Create a new Azure Blob storage resource** > in the new window titled **Create a storage account**, under the **Basics** tab, ensure the fields **Subscription** and **Resource group** are set to the default values. Under **Instance details**, set a name for **Storage account name**. Leave the rest of the fields as is. Select **Review + create**. Under the **Review + create** tab, select the **Create** button. The Azure Blob Storage resouurce will take a moment to deploy.
   
   c. Navigate back to the window for **Chat playground**. Select the refresh button next to the field **Select Azure Blob storage resource** > select the resource you made in step b above. Select the button **Turn on CORS**.
   
10. For the field **Select Azure AI Search resource**, select  **Create a new Azure AI Search resource**. Select a **Service name**> Ensure all fields are set to it's default values > select **Review + create** > **Create**. The Azure AI Search resource will takea moment to deploy.
11. Navigate back to the window for **Chat playground**. Select the refresh button next to the field **Select Azure Blob storage resource** > select the resource you made in step 4 above.
12. Enter a name for the field **Enter the index name** > **Next**.
13. In the **Upload files** section, select **Browse for a file** > In the file explorer, navigate to **Documents** > select all three files: **ContosoAI ChipEnhance Perks Program.docx**, **ContosoAI Insurance Plans.docx**, and **Overview of ContosoAI.docx** > the three file should now be present in the **Upload files** page of the window > select **Upload Files** > **Next**.
14. Under the **Data management** section, leave everything as default and select **Next**.
15. Under the**Data connection** select **API key** > **Next** > **Save and close**.
16. In the **Chat playground** window, select **View code** which is in the ribbon at the top left of the window.
17. In the **Sample code** window select the drop down to the right of the first field and select **json**> switch to the **Key authentification**tab:
    
    a. Copy and paste the following values, as you will need them in the upcoming tasks: **Endpoint**, **API key**, and **Azure Search Resource Key**. You can also leave this window open to collect these values for the upcoming tasks. 

       

## Task with subtasks

Sometimes you might want to break a taak down into smaller chunks.

### Subtask 1

1. Step 1
1. Step 2
1. Etc.

### Subtask 2

1. Step 1
1. Step 2
1. etc.

## Clean up

<!-- Good practice - especially as self-paced learners will be using their own subscriptions -->
<!-- Delete this section if it is not needed -->

Now that you've finished the exercise, you should delete the cloud resources you've created to avoid unnecessary resource usage.

1. Step 1
2. etc.
