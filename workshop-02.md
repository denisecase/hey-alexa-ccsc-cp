# Workshop 02 - Introducing Alexa Skills (20 minutes)

   - Alexa Developer Account & Console
   - One Skill Invocation 
   - Many Interactions/Intents
   - Endpoints

---

## Invocation - One Skill - Bearcat Buddy Football

- Invocation: bearcat buddy football
- User says: "Alexa, open Bearcat Buddy Football"

---

## Interaction - Many Intents


2 Custom Intents

- Next Intent  (asking about next game)
- Remaining Intent (asking about how many remain)

Next Intent asks about the next event - utterances might include:

- "When is the next home game?"
- "When is the next away game?"
- "When is the next {Location} game?"
- "Where is the next {Location} game?"
- "Next game?"

Remaining Intent asks about remaining events - utterances might include:

- "How many home games remaining?"
- "How many away games remaining?"
- "How many games remaining?"
- "How many {Location} games are there?"
- "How many {Location} games are left"
- "How many more games are there?"
- "Remaining games?"

Also: Five Amazon Built-In Intents (No Work Required)

- Intents / AMAZON.FallbackIntent
- Intents / AMAZON.CancelIntent
- Intents / AMAZON.HelpIntent
- Intents / AMAZON.StopIntent
- Intents / AMAZON.NavigateHomeIntent

Intent SLOTS enable Enumerated Types (e.g. home/away)

- In the intent, create an intent "slot" - in this case, "location". 
- Then, we setup a slot type with possible values (home/away)

- Slot Types / LocationSlotType 
  - Value "home"
  - Value "away"

Slots make it much more efficient to define sample utterances. 

---

## Endpoints - Where the Magic Happens (Logic to handle requests) 

Serverless endpoints (URLs) to handle requests (launch, intents, end)

- Launch Request Handler (start)
- SessionEnded Request Handler (end)

- Next Intent Handler
- Remaining Intent Handler
- 
- Help Intent Handler
- CancelAndStop Intent Handler 

More...

- Error Handler
- Lambda Handler (no name entry point)

