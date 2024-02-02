# Demo Azure Open Ai Assistants
![Azure openAi assistants ](./assets/assistant.jpeg)

this demo is based on this page  [Learn Microsoft website](https://learn.microsoft.com/en-us/azure/ai-services/openai/assistants-quickstart?branch=pr-en-us-264938&tabs=command-line&pivots=programming-language-python#create-your-first-assistant)

## Create your first assistant

### What's an assistant?

An assistant ( or many !) can perform a wide range of tasks, such as answering questions, providing recommendations, and executing commands 

An assistand could have some tools :
- based on files ( retrieval)
- code interpreter
- functions, Apis 

You can use assistants to build a wide range of applications, such as chatbots, virtual agents, and more.

In clear you could create in a few line of code some assistant with tool to create a pipeline of threads in order to adresse an ask or demand of the user.

You can in fact create multiple assistants with different tools and diffrent thread (async or not) to adress the demand of the user.

And you will retrieve response in json format. where you can make some process or create orchestrate with :
- Thread id
- Message id
- assistant id

> Multi-Assistant Thread Runs with parallel function calls


### Prerequisites

you will need :
- python 3.8 or later
- visual studio code and plugins for python and notebook
    - Jupyter / jupyter Keymap / jupyter Cell Tags
    - Jupyter Notebook renderers
- An azure subscription 
- Access to azure openAi service
- Access to the lastet gpt4 1106 model ( Actually deployed actually in sweden , east us and west us 2)
    - you can refer to this link for the avaibility of model in region [Azure OpenAi model](https://docs.microsoft.com/en-us/azure/ai-services/openai/region-availability)
- Deploy the service in portal azure for Azure open Ai service in the region accordly
- Make a deployment of the model in the [azure openAi service Ai studio](https://oai.azure.com/), give a name of deployment

For the name of the deployment ( you gave a name normally ) in Azure Ai studio, you can find it in the deployment section of the model if you don't remind it
![image](./assets/azuredeployment.png)

You have to correctly modify the information in the secrets_env renamed in secrets.env
> the azure endpoint and the azure key aoai could be found in your azure portal
![image](./assets/portailazurekeyaoai.png)
or
> directly in the conversation category in Ai studio ,with the model selected and the button code clicked in first step
![Button code in Azure Ai studio](./assets/aistudiobuttoncode.png)
And after you will have to click on the button "show secret" to obtain the key and the endpoint is displayed in the example code
![image](./assets/endpoint&token.png)

You will have to click on each code step by the play button.

it there is no errors you will obtain at the last cell this json dump with the result and all the informations gathered 
![Result Json](./assets/resultjson.png)

When you are ready you can follow the steps in AzureAOAI.ipynb notebook
> In my case the gpt4 1106 is named  **gpt-4turbo**

You could now use the notebook python to launch the demo.

## DeepDive Aassistant instance

### how the interaction with the assistant is done

So you have instantiante an assistant ?
You have to understand how manage thread and message ?

### format of the message json

![Result Json](./assets/resultjson.png)

### Params of the assistant
Extract from  openAi [library python](https://github.com/openai/openai-python/blob/main/src/openai/resources/beta/assistants/assistants.py

Tools :
A list of tool enabled on the assistant. There can be a maximum of 128 tools per
  assistant. Tools can be of types `code_interpreter`, `retrieval`, or `function`.
