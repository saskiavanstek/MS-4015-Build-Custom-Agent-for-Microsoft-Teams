
lab:
'Create a Custom Agent'
---
<!--
Edit the metadata above to manage the list of exercises in the home page of the GitHub site that gets generated.
You can delete the module and edit index.md in the root of the repo to customize the display so that only the exercises are listed
To enable GitHub page publishing, edit the Page settings for the repo and publish from the main branch
-->

# Create and test a Custom Agent

In this exercise you will create an Azure OpenAI resource that serves as the foundation for creating your custom agent.

This exercise should take approximately **60** minutes to complete. <!-- update with estimated duration -->

**Note:** Learners can complete this lab with these options
1) A lab environment provided for the learners.
2) Learners are expected to complete this lab on their own environments for all other ALHs.

##  Task 1: Create Azure OpenAI resource 

First, you need to ...

1. Navigate to **https://portal.azure.com** in your edge browser.
1. Sign into the azure portal.
2. Click on **+ Create a resource** on the upper left hand  side of the screen.
1. In the search box type in **azure openai** and press enter.
1. A result called **Azure OpenAI** should appear as an option. At the bottom left hand corner of this option is a button labeled **Create**. Press> **Create** > **Aure OpenAI**.
1. Under the page **Create Azure OpenAI** set the following fields:

**Note:** For learners using their own environment, learners will have to use their own discretion when selecting values for fields **Subscription** , **Pricing Tier** and **Resource Group**. For learners using the provided lab environment, select the default values for the fields in steps a-d below.
   
   a. **Subscription** Azure Subscription -- IT-M365 Training.
   
   b. **Resource Group** : Use RG-MS4015-StudentXX (Where XX is your studentnumber).
   
   c. **Name** : Type in any name you choose.
   
   d. **Pricing tier**: the default value  is **Standard S0**, but Use your own discretion when filling this field.
   
Select **Next**.

7. Under the next page, in the **Network** tab, Select the option **All networks, including the internet, can access this resource.**
Select **Next**.
8. Under the next page in the **Tags** tab, leave the Name and Value fields blank.
Select **Next**.
9. Under the next page, in the **Review + submit** tab, press **Create**.
10. You will be taken to a page where this newly created Azure OpenAI resource is being created. You will see the words **Deployment in progress**. Wait for a few second for this resource to finish deploying. Once the resource is deployed, click on the button **Go to Resource**.
11. **Result:** You will now be in the page with newly created Azure OpenAI resource. You can verify by checking the name of the resource in the top left hand corner of the page. This name should match the name you chose for step 5c above.


## Task 2: Implement RAG for the Azure OpenAI model

In this task, you will learn how to implement RAG using a data source for your own test environment.

1. In the page for your newley created Azure OpenAI resource, click **Go to Azure AI Foundry portal** in the ribbon at the top of the page.
2. In the new page titled **Chat playground**, under **Setup**, select **+ Create new deployment** > **From base models**.
3. In the pop up window titled **Select a chat completion model** scroll down and select the option **gpt-4o** > **Confirm**.
4. In the **Deploy model gtp-4o** window, leave everything in it's default setting and select **Deploy**.
5. In the **Chat playground** page, select **Add your data** located near the bottom of the screen > **+ Add a data source**.
6. In the **Select or add data source** window, select  the dropdown for **Select data source** and select **Upload files (preview)**.
7. In the next page for **Data source**, ensure the dropdown for **Select data source** is set to **Upload files (preview)**

**Notes:** For learners using their own environment, users may have to use your own discretion when filling out fields for steps a-c below. For Learners using the provided lab environment, follow use the default values as instructed in steps a-b below. 
  
   a. In the **Subscription** field, ensure the default value is selected.
   
   b. In the **Select Azure Blob storage resource** field, select **Create a new Azure Blob storage resource** > in the new window titled **Create a storage account**, under the **Basics** tab, ensure the fields **Subscription** and **Resource group** are set to the default values-choose the only value available for **Resource group**. Under **Instance details**, set a name for **Storage account name**. Leave the rest of the fields as is. Select **Review + create**. Under the **Review + create** tab, select the **Create** button. The Azure Blob Storage resource will take a moment to deploy.
   
   c. Navigate back to the window for **Chat playground**. Select the refresh button next to the field **Select Azure Blob storage resource** > select the resource you made in step b above. Select the button **Turn on CORS**.
   
8. For the field **Select Azure AI Search resource**, select  **Create a new Azure AI Search resource**.  Ensure the fields **Subscription** and **Resource group** are set to values of your choosing.

   **Note:** For learners using their on environment, please use your own discretion when selecting values for fields **Subscription** and, **Resource Group**.

9. Click the dropdown value for **Resource Group** to select the option of your choosing. Input a **Service name**> Ensure all other fields are set to it's default values > select **Review + create** > **Create**. The Azure AI Search resource will take a moment to deploy.
10. Navigate back to the window for **Chat playground**. Select the refresh button next to the field **Select Azure Blob storage resource** > select the resource you made in step 9 above.
11. Enter a name for the field **Enter the index name** > **Next**. Copy and paste this name somewhere accessible as you will need this in the upcoming tasks.
12. In the **Upload files** section, select **Browse for a file** > In the file explorer, navigate to **Documents** > select all three files: **ContosoAI ChipEnhance Perks Program.docx**, **ContosoAI Insurance Plans.docx**, and **Overview of ContosoAI.docx** > **Open** > the three file should now be present in the **Upload files** page of the window > select **Upload Files** > **Next**.
13. Under the **Data management** section, leave everything as default and select **Next**.
14. Under the**Data connection** select **API key** > **Next** > **Save and close**.
15. In the **Chat playground** window, select **View code** which is in the ribbon at the top left of the window.
16. In the **Sample code** window select the drop down to the right of the first field and select **json** > switch to the **Key authentification**tab:
    
    a. Copy and paste the following values, as you will need them in the upcoming tasks: **Endpoint**, **API key**, and **Azure Search Resource Key**. You can also leave this window open to collect these values for the upcoming tasks.

 ## Task 3: Create and test custom agent in Test Tool and Teams

In this task you will create the custom agent and test the agent.

1. Open **Visual Studio Code**.
2. In the right hand side of the visual studio code window select the **Teams Toolkit** icon > select **Create a New App** > in the dropdown select **Custom Engine Agent** (note: depending on the Teams Toolkit version, you may have to select **Custom Copilot**) > **Basic AI Chatbot** > **JavaScript** > **Azure OpenAI** .
3. In the blank box at the top of the screen, first enter :

   a. **API Key** from the previous task > **Enter**.

   b. **Endpoint** from the previous task > **Enter**.

   c. For **Azure Open AI deployment name** type in **gpt-4o** > **Enter**.

   d. For **Choose the folder where your project room folder will be located**, select **Default folder**.

   e. For **Input application name** type in any name > **Enter**> in the pop up window select **Yes, I trust the authors**.

   f. In the new VS Code window of the newly created app from steps a-f above, navigate to the **Teams Toolkit** icon on the left hand side of the screen.

   **Note:** steps g-i should be for completed for a user's environment that does not have admin access to the Microsoft Teams Admin Center and/or for Learner's using the provided lab environment.


   g. Under the **Accounts** section, click **Sign in to Microsoft 365**. A new window in your browser will open. Login using the credentials provided.

   h. Navigate back to the VS Code page of your app. You should now see a green check mark by the words **Custom App Upload Enabled** under **Accounts.

   i. Under the **Accounts** section, click **Sign in to Azure**. Click **OK** on every pop up window. A new window in your browser will open. Login using the credentials provided.
   
4. Navigate to **src/prompts/chat/skprompt.txt** in the VS Code window of your app. Delete any text in the file and paste the following:
 "The following is a conversation with an AI assistant, who is an expert on answering questions over the given context. 

Responses should be in a short journalistic style with no more than 80 words." 

5. Navigate to **config.json** file under prompts/chat in the VS Code window of your app. Delete the code currently present in the brackets and paste the following code in the brackets.

```json
"data_sources": [ 
    { 
        "type": "azure_search", 
        "parameters": { 
            "endpoint": "AZURE-AI-SEARCH-ENDPOINT", 
            "index_name": "YOUR-INDEX_NAME",
            "in_scope": false,
            "authentication": { 
                "type": "api_key", 
                "key": "AZURE-AI-SEARCH-KEY" 
            } 
        } 
    } 
]
```

6. In the code above, replace the following with the values you saved from the previous task (note: the values must be in quotation marks):

   a. **AZURE-AI-SEARCH-ENDPOINT** is the **Endpoint** from the previous task.

   b. **index_name**  is the **Index name** from Task 2 step 11 in the previous task.

   c. **key** is the **Azure Search Resource Key** from the previous task.

7. Go to **src/app/app.js file** and add the following variable inside **OpenAIModel** right after the line azureEndpoint: config.azureOpenAIEndpoint, : 

    a. azureApiVersion: '2024-02-15-preview',
   
8. **File** > **Save all**
    
9. Press **Ctrl+Shift+d** on your keyboard an a dropdown at the top left  will appear that has a green play button and the word Debug > Select the dropdown> select **Debug in Test Tool** > Press **F5**.
10.Custom engine agent runs within the Debugging tool you have chosen, which opens in your browser. You can ask the bot any questions pertaining to the RAG data uploaded in Task 2 step 12.
11. Navigate back to the VS Code window for your app. Select the **Debug** button dropdown and select **Debug in Teams (Edge)** then press **F5** or the gren play button.
13. A new window in your Edge browser will open. You will be prompted to sign in. Use the login information provided to sign in. After successfully signing in, close the window.
14. Repeat step 11 again. There should be a window with the title of your newly created app. Select **Add** > **Open**.
15. Congrats! You can now ask the agent any question pertaining to the RAG data files.
16. **Note:** For Learners completing this lab on their own environment, this agent was made for educational purposes using your own subscription, users should proceed with deleting the agent after completion of this lab. To delete a custom agent in Microsoft Teams, you can:
- Select the agent you want to delete, then choose the **More options icon (…)** and select **Delete**.
- Remove the agent from a chat by selecting the ellipses in the thread and choosing **Manage Apps**.
- From the authoring experience of an agent, select the **ellipses (...)** and choose **Delete**.- From the authoring experience of an agent, select the **ellipses (...)** and choose **Delete**.

**END OF LAB**


**END OF LAB**
