# IBM Cloud :cloud:

# Conversation: Build your own bot with Watson.
 
## Introduction
This exercise will show you how to create your own Slack bot using Watson conversations service on IBM Bluemix. 

#### About IBM Cloud
IBM Cloud, formerly known as Bluemix, is an open-standard, cloud-based platform for building, managing, and running applications of all types (web, mobile, big data, new smart devices, and so on).
- The developer can choose any language runtime or bring their own. Zero to production in one command.
- A catalog of IBM, third party, and open source API services allow the developer to stitch an application together in minutes.
- Development, monitoring, deployment, and logging tools allow the developer to run the entire application.
- Sign up in minutes. Pay as you go and subscription models offer choice and flexibility.

#### About Node-RED
Node-RED is a visual tool for wiring the internet of things - connecting hardware devices, APIs and online services in a new and interesting way. Node-RED provides a browser-based flow editor that makes it easy to wire together flows using the wide range nodes in the palette. Flows can be then deployed to the runtime in a single-click.
- JavaScript functions can be created within the editor using a rich text editor.
- A built-in library allows you to save useful functions, templates or flows for re-use.
- See https://nodered.org for more information. 

#### Prerequisites
-	Register to IBM Cloud at https://bluemix.net
  
 
## Step 1. Watson Conversations
The new Watson Conversation API makes it easy to build a bot. Watson combines a number of cognitive techniques to help you build and train a bot to automate conversation, all via dramatically simplified tooling that practically anyone can use. You can then deploy your Watson chat-bot via mobile device, messaging platform like Slack, or even through a physical robot.

With the IBM Watson™ Conversation service, you can create an application that understands natural-language input and uses machine learning to respond to customers in a way that simulates a conversation between humans.

# Create your Watson conversations service on Bluemix
Go to your IBM Cloud account and open the catalog. Look for Watson Conversations service and click on it.  (If you previously created a Conversation service, you can use that.)

![](/screenshots/Picture1.png?raw=true)

You don't need to change the name if you don't want to, just click on 'Create'. 
In this case, this service will not be binded to any application. Choose the region and space where you want the service to be created. Your organization will be filled by default.

![](/screenshots/Picture2.png?raw=true)

Once the service is created click on 'Launch tool' to access it. 

![](/screenshots/Picture3.png?raw=true)
 
Click on Log in with IBM ID and you will automatically access the service. It uses your IBM Cloud ID and password.

![](/screenshots/Picture4.png?raw=true)
 
# Create a workspace

The natural-language processing for the Conversation service happens inside a workspace, which is a container for all of the artifacts that define the conversation flow for an application. A single Conversation service instance can contain multiple workspaces.

You can create a workspace and start from scratch or import an existing conversation. 
Let's start by importing a conversation. Download the PizzaOrder.json file. 

Click on the import icon shown in the image below. 

 

When you import a workspace, you can choose to import only the intents and entities, which can be useful if you want to build a new dialog using the same training data. In this case we will import everything.

Navigate though the sample and test the conversation in the dialog tab. 

 
Now you can start creating your own bot conversation! 

# Create your own conversation

Click on create to start your own conversation. 
 

Give your workspace a name and choose the language for your bot. The available languages are: Arabic, German, English, Spanish, French, Italian, Japanese, Korean, Portuguese, Czech, Dutch and Chinese. If you want to create a bot in another language leave the default configuration with English. Then click on 'Create'.
 

Now you can start creating your own intents, entities and dialog flow. 

Each workspace contains the following types of artifacts:
- **Intents:** An intent represents the purpose of a user's input, such as a question about business locations or a bill payment. You define an intent for each type of user request you want your application to support.
In the user interface, the name of an intent is always prefixed with the # character.
To train the workspace to recognize your intents, you supply lots of examples of user input and indicate which intents they map to.

- **Entities:** An entity represents a term or object that is relevant to your intents and that provides a specific context for an intent. For example, an entity might represent a city where the user wants to find a business location, or the amount of a bill payment.
In the user interface, the name of an entity is always prefixed with the @ character.
To train the workspace to recognize your entities, you list the possible values for each entity and synonyms that users might enter.

- **Dialog:** A dialog is a branching conversation flow that defines how your application responds when it recognizes the defined intents and entities.
You use the dialog builder to create conversations with users, providing responses based on the intents and entities that you recognize in their input.

As you add information, the workspace trains itself, so you don't have to do anything to initiate the training.

# Intents
To plan the intents for your application, you need to consider what your customers might want to do, and what you want your application to be able to handle. Choosing the correct intent for a user's input is the first step in providing a useful response. The intents you identify for your application will determine the dialog flows you need to create; they also might determine which back-end systems your application needs to integrate with in order to complete customer requests (such as customer databases or payment-processing systems).

Check this video to about creating intents: https://youtu.be/DmvN6ZJrZE4

For example: 
Create the intent #greetings, and write all the possible ways your bot users will greet the bot. 
Hello, hi, hola, moi, good morning, good afternoon…. Etc. 
          

# Entities
An entity represents a term or object in the user's input that provides clarification or specific context for a particular intent. If intents represent verbs (something a user wants to do), entities represent nouns (such as the object of, or the context for, an action). Entities make it possible for a single intent to represent multiple specific actions. An entity defines a class of objects, with specific values representing possible objects in that class.

Check this video about creating entities: https://youtu.be/oSNF-QCbuDc 


# Dialog

A dialog uses the intents and entities that have been identified, plus context from the application, to interact with the user and ultimately provide a response.
The response might be the answer to a question such as Where can I get some gas? or the execution of a command, such as turning on the radio. The intent and entity might be enough information to identify the correct response, or the dialog might ask the user for more input that is needed to respond correctly. For example, if a user asks, "Where can I get some food?" you might want to clarify whether they want a restaurant or a grocery store, to dine in or take out, and so on. You can ask for more details in a text response and create one or more child nodes to process the new input.
The dialog is stateless, meaning that it does not retain information from one interchange to the next. Your application is responsible for maintaining any continuing information. However, the application can pass information to the dialog, and the dialog can update the context information and pass it back to the application.

Check this video about creating dialogs: https://youtu.be/3HSaVfr3ty0 


# Export & import a workspace
Exporting a workspace saves a copy of all workspace data in a JSON file. Use this option if you want to import the workspace into a different service instance or save a copy of the workspace data offline. 

Export the JSON file directly from your Watson Conversations dashboard by clicking in the three dots and selecting 'Download as JSON'.
 
In the free version of the Conversation service you will only be able to have 5 workspaces at the same time.  The Standard version allows up to 20 different workspaces at the same time. 

# Testing your dialog

As you make changes to your dialog, you can test it at any time to see how it responds to input.
1.	From the Dialog tab, click the   icon.
2.	In the chat panel, type some text and then press Enter.
Tip: Make sure the system has finished training on your most recent changes before you start to test the dialog. If the system is still training, a message appears at the top of the chat pane:
 
3.	Check the response to see if the dialog correctly interpreted your input and chose the right response. 
The chat window indicates what intents and entities were recognized in the input. In the dialog editor pane, the currently active node is highlighted
 
As you continue to interact with the dialog, you can see how the conversation flows through the dialog.
If you determine that the wrong intents or entities are being recognized, you might need to modify your intent or entity definitions. If the right intents and entities are being recognized, but the wrong nodes are being triggered in your dialog, make sure your conditions are written correctly.

# Get your credentials 
In this example, we will need your Watson conversation credentials and your workspace ID. Save these credentials, because we will need them later in Step 3. 

1.	Get your workspace ID
In your Watson Conversations service workspace dashboard click on the three dots to view the details of your workspace and then copy your workspace ID.  
Note: The ID showed in this document does not work, use your own. 
    

2.	Watson Conversations credentials 
In IBM Cloud open your Conversation service and click on 'Service credentials'.
 


Click on 'View credentials' to get your password and username. If you don't see any credentials click on 'New credential'. 


If you want to read more about how to build your conversation with Watson check the official documentation:

https://www.ibm.com/watson/developercloud/doc/conversation/index.html 
 
## Step 2. Create Your Node-RED Application
1. In a browser navigate to https://bluemix.net
2.	Select 'LOG IN' then enter your log in information and press 'SIGN IN'.  You should be seeing your dashboard view:
 

3.	Select the 'CATALOG' view.
4.	Locate the NODE-RED Starter in the boilerplate section (Apps í Boilerplates) of the catalog and click on it. 
 

5.	Enter a name for your application, as shown below (host will automatically be completed).  The host name must be unique on IBM Cloud, so please choose a name with your company name or initials to try to make a unique name.  Press 'CREATE'. 
 
6.	Your application is now staging and will be up and running in a short while. Press 'OVERVIEW' to see information about your application.

7.	When fully staged, click on the View app link, next to the green circle, this launches the Node-RED main page. 

8.	Configure your Node-RED editor. In this section, you will set up a username and password to protect your flow. 

 

9.	Write an username and a password of your choice and click 'Next'. Remember that it does not have to be related to your IBM Cloud ID. 
 
Node-RED is an open source project so you can add new nodes to the palette by modifying the package.json file. We will do this later on in the lab. 

 
 
#### Your Node-RED flow is all set! Enter your credentials to access the editor.

 
Now click Go to your Node-RED flow editor to open the flow editor.
 


10.	When using Node-RED we build our apps using this graphical editor interface to wire together the blocks we need. We can simply drag and drop the blocks from the left menu into the workspace in the center of the screen and connect them to create a new flow. 

Note: If you get an "Authorization denied" message when deploying your applications make your sure you are logged in. Click on the icon on the top right side of the Node-RED canvas and login with the credentials you created in the previous steps. 

 
## Step 3. Add new nodes to your application
You can add new nodes using the continuous delivery option, and creating a GIT repository in the cloud to modify the application's source code. In this example, we are going to add new nodes to the Node-RED palette directly from the Node-RED window. 

In the Node-RED window click on the three lines on the top right corner and in the menu, click on the "Manage palette". This will open the node menu where you can add new nodes to your application. You will see the nodes that are installed by default and if you go to the 'install' tab you can search for any node package and add it directly to your app.
                   

Search for the dashboard nodes by writing 'dashboard'. This will return multiple node packages, you need to install the package 'node-red-dashboard'. Find it in the search results and click on install. 

 
This will prompt a window to confirm the installation. Click on install and wait few minutes, the application may require a restart. Click "Done" to close the left side menu. 

 
After few minutes you will see the new nodes in your Node-RED palette. 

 
## Step 4. Build the Node-RED flow
In this section we will build a simple flow to represent our user interface and connect it with our conversation. Access your application Node-RED workspace by clickin on your application URL.

The flow we are going to build will look like this:
 
Copy the content of the bot-with-ui.txt file.

Import the flow by simply clickcing on the 3 white lines on the top right corner of the Node-RED window.  Import - Clipboard - and paste the text you copied from above. 
 
 
This will create an exact flow as shown in the first picture of this section. You will need to do some editing on few nodes. 

Edit the conversation node with your own credentials. You can find the credentials in the IBM Cloud dashboard where you launched the convesation service (show in step 1.1). You will also need the workspace ID. This can be found inside the Watson Coversation service. 
 
Deploy your application changes from the Deploy button on the top right side of the screeen. 
 
## Step 5. Test your bot
See the result of your application by accessing the UI.
Go to the UI tab and chat with Watson!

http://yourAppName.mybluemix.net/ui - US South

Remember that if you are in UK or Sydney the addredd will look slightly different:
http://yourAppName.eu-gb.mybluemix.net/ui - UK

http://yourAppName.eu-de.mybluemix.net/ui - Germany

http://yourAppName.au-syd.mybluemix.net/ui - Sydney

 
#### Congratulations, you have created a chatbot!

