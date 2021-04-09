# Workshop 03 - Introducing AWS and Hosting Functions (20 minutes)

   - Amazon Web Services Account
   - Lambda Serverless Functions
   - Skill Code 
   - Editing / Updating Function Code

---

## Amazon Web Services Account

Recently integrated into the Alexa Developer Console for easier access - just accept the prompt to begin creating your functions here.

## Lambda Serverless Functions

Don't need to understand much about 'serverless' functions - they are just what the name implies. 
Allows us to build and host functions easily - we don't care what OS or Server. 
Our examples are in Node (server-side JavaScript), but when building additional functions, you can choose Python as well. 
If you build and host endpoints elsewhere, additional langages like Go are available as well. 

## Skill Code

- package.json - provided / not editiable
- util.js - provided / not editable
- index.js - a default is provided - we will modify and extend this
- games.json - we add a "New File" to hold the game information. 

As you follow this example, the only thing you will need to update is the game data. 
No need to write custom code. 
Just create a custom invokation for your favorite sports team and update the information in the games file. 

### index.js

1. Require the sdk (lines 1-4)
2. Configure your constants (6-18)
3. Require the games.json data file (20-21)
4. Copy the helper function to "get next" (24-50)
5. Copy the helper function to "get remaining" (53-81)

Handlers

Each handler takes in a "HandlerInput" object, providdes a custom ResponseBuilder that can speak and listen for more

1. LaunchRequestHandler (on start) - update speakOutput if desired
2. NextIntentHandler - the first of our custom Intent Handlers
3. RemainingIntentHandler - the second of our custom Intent Handlers
4. HelpIntentHandler - update speakOutput if desired
5. CancelAndStopIntentHandler - update speakOutput if desired
6. SessionEndedRequestHandler (on end)
7. IntentReflectorHandler - for debugging - update speakOutput, comment out reprompt
8. ErrorHandler - say what? - update speakOutput if desired

Constructor

1. Add custom handlers
2. Remove unneeded handlers (e.g. HelloWorldIntentHandler)

```Node
// The SkillBuilder acts as the entry point for your skill, routing all request and response
// payloads to the handlers above. Make sure any new handlers or interceptors you've
// defined are included below. The order matters - they're processed top to bottom.
exports.handler = Alexa.SkillBuilders.custom()
    .addRequestHandlers(
        LaunchRequestHandler,
        NextIntentHandler,  //  add custom intents and remove any unnecessary ones (e.g. hello world)
        RemainingIntentHandler, //  add custom intents and remove any unnecessary ones (e.g. hello world)
        HelpIntentHandler,
        CancelAndStopIntentHandler,
        SessionEndedRequestHandler,
        IntentReflectorHandler, // make sure IntentReflectorHandler is last so it doesn't override your custom intent handlers
    )
    .addErrorHandlers(
        ErrorHandler,
    )
    .lambda();
```

## Editing / Updating

- Click "Save"
- Click "Deploy to live"

Test by going back and forth between "Code" and "Test" tabs.

- Error messages are marked with red x. Messages are typically helpful. 
- Warnings are marked with yellow. Good static analysis tools - e.g., found == - don't you want === which is an excellent JavaScript suggestion.

Local testing (not required)

- Not required, but I keep a copy of my code in a GitHub project. 
- After cloning down to your machine (or copying your files down).
- In the lambda folder (you'll need Node/npm installed).

Open PowerShell in the folder with your index.js file. 

Just once, run ```npm init``` and answer the prompts to create a local minimal package.json (required by Node.js).
After debugging, run ```node index.js``` to start your app.

---

[:arrow_backward: Back ](./workshop-02.md) • [Next :arrow_forward:](./workshop-04.md)

---

![Alexa Developer Console - Code Tab](./images/alexa-developer-console-code-tab.PNG)
