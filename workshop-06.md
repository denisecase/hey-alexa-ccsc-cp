# Workshop 06 - Working through Alexa Build Tasks (30 minutes)

1. Design your skill
2. Build your skill

## Design - Fill in these questions first! 

1. How will you invoke your skill? e.g., Alexa - open Bearcat Buddy Football. Don't be too general! Many sports in one skill is too complex - be specific. 
2. What custom intents will this skill handle? (In our case, NextIntent and RemainingIntent.)
3. For each intent, what utterances (what might the user say)?
4. Could the utterances (prompts) use any slots? (Yes - a location slot could be either home/away or omitted). 
5. For each slot (e.g. {Location}), create a slot type and list the associated values (home or away). 
6. Your skill NAME should be the invocation but with proper captilazation (e.g. Bearcat Buddy Football).

## Build

1. Log in to the Alexa Console.
2. Click "Create Skill"

### Create Skill

1. Skill name: Bearcat Buddy Womens Golf
2. Model: Custom
3. Method: Alexa-Hosted (Node.js)
4. Scroll up & click "Create Skill"

Choose Template

1. Template: Start from Scratch
2. Click "Continue with Template"

It'll take a minute...

### Build Tab - Invocation

1. Invocation: bearcat buddy womens golf

---

### Build Tab - Interaction Model - Custom Intent 1 - NEXT

1. Click Add Intent
2. Name: NextIntent
3. Click "Create custom intent"

NextIntent - Sample Utterances

Hit enter after typing each entry. 

1. next game
2. when is the next game
3. where is the next game
4. when is the next {Location} game
5. where is the next {Location} game

### Build Tab - Interaction Model - Custom Intent 2 - REMAINING

1. Click Add Intent
2. Name: RemainingIntent
3. Click "Create custom intent"

RemainingIntent - Sample Utterances

Hit enter after typing each entry. 

1. how many games remaining
2. how many more games are there
3. how many {Location} games remaining
4. How many {Location} games are there
5. How many {Location} games are left

---

### Build Tab - Slot Types - LOCATION SLOT TYPE

1. Click "Add Slot Type"
2. Name: LocationSlotType
3. Click "Next"

Slot values

Hit enter after typing each entry.

1. home
2. away

--- 

### Build Tab - Custom Intents - Select slot type

1. Click custom NextIntent
2. Set Location to slot type LocationSlotType
3. Click custom RemainingIntent
4. Set Location to slot type LocationSlotType
5. Click Save Model (at the top)

### Build Model

1. Click "Build Model" button
2. Click "Evaluate Model" button and test utterances as you like. 

[:arrow_backward: Back ](./workshop-05.md) • [ Next :arrow_forward:](./workshop-07.md)

---

![Alexa Developer Console - Custom Intent - Utterances and Slot Types](alexa-developer-console-custom-intent-utterances-and-slot-types)
