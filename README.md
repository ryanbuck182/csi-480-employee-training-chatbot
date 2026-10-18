# PROJECT 1A: AI-Powered Employee Training Chatbot    
###### Ryan Buck and Akiva Nugent
###### Champlain College: CSI-480 - Topics in AI 
###### Dr. Gowda
<br>

---

## Context
You are a new employee at a mobile phone store. An angry customer has just walked up to the counter with a mobile device that won't turn on. 

Your job is to assist the customer with their problem. You must stay professional, figure out what is wrong, and resolve the support within store policy. 

This simulation is graded. A final score will be provided at the end of the simulation.


## Scenario and Behavior
At the start of each simulation, one plausible customer-issue scenario is picked at random. The customer knows only what a layperson would: That their phone is broken, clearly observable behavior, clearly visible physical condition, and the device's recent history. They will not volunteer this information however -discovering that information is your job. 

The customer will start hostile. Depending on your level of care, the customer's mood may shift. Empathy, professional language, and productive help will be your best recourse in calming the customer's temper. Accusatory dismissive, or rudeness will make them angrier. 

### Your Goals and Expectations
1. Diagnose the Problem: Ask diagnostic questions politely to figure out what is wrong (water exposure, extreme heat, physical damage) without sounding accusatory:

| Offensive/Accusatory                       | Neutral/Diagnostic                                                          |
|--------------------------------------------|-----------------------------------------------------------------------------|
| "Did you drop it in water?"(assumes blame) | "Has the phone had any contact with water or moisture recently?"            |
| "You probably left it in the sun."         | "Was the phone exposed to high heat, like direct sunlight or a hot car?"    |
| "Did you break it?"                        | "can you walk me through what happened right before it stopped turning on?" |

2. Decide whether the phone is repairable
3. Make an offer within the store policy

### Store Policy - Allowed Resolutions

| Diagnosis                    | Allowed Offer                                                  | Discount Available                        |
|------------------------------|----------------------------------------------------------------|-------------------------------------------|
| The device is not repairable | A new phone _only_ if the customer trades in the broken phone. | up to 30%                                 |
| The device is repairable     | Replaced damaged parts, and repair                             | up to 40% on parts <br> no labor discount |

Any offer made beyond these limits -even if well intentioned- is against store policy and will result in a deduction from your score. 
(ex. 50% off / any % off on labor / phone discount without a trade in)

If the customer asks for a discount before a diagnosis has been made, decline to give any firm commitments until the requirements have been fulfilled. 

### Reference: Common Causes of Damage
| Symptoms/History                                                     | Likely Cause                            | Repairable? |
|----------------------------------------------------------------------|-----------------------------------------|-------------|
| No Power <br> corrosion on port <br> customer mentions body of water | Liquid damage <br> corroded logic board | Often not   |
| No power <br> phone was in hot car <br> swollen battery              | Heat damage <br> battery swelling       | Sometimes   |
| No power <br> recent hard drop <br> cracked screen                   | Physical/Impact damage                  | Often       |
| No power <br> slow decline over weeks <br> old phone                 | Battery end-of-life                     | Usually     |
| No power <br> briefly flickers on                                    | Software/firmware issue                 | Usually     |

### Scoring Rules
The customer's starting attitude is hostile. The goal is for the employee to bring satisfaction to at least 8/10 by the end of the interaction
- Violations (rude language, refusing to engage, going off-topic) count against the employee.
- 3 violations → the customer walks out. Final rating: 1/10, with negative feedback.
- Issue never resolved (no diagnosis, no offer, conversation stalls) → Final rating: 2/10.
- Handled well → rating between 8 and 10, with specific positive/constructive feedback.

## How to Run It
1. Install dependencies if you do not already have them. This can be done via the terminal or in a code-block containing:
```
%pip install openai gradio pydantic python-dotenv
```
**Note: Make sure your OpenAI install is up to date. If not, the code may run, but fail after you submit a message**
<br>


2. Provide your own OpenAI API key. 
We do not provide OpenAI API keys ourselves. If you do not already have access to your own, you can make an account and [get them here](https://platform.openai.com/login?next=%2Fapi-keys). Create a file named ```.env ``` in the same folder as the notebook. Contents should mirror ```.env.example ```:
``` OPENAI_API_KEY= [YOUR KEY HERE] ```

3. Open ```Project1.ipynb``` and press **Run All**. The last cell launches the client interface. If a browser is preferable, the local link will be printed below the final block.
   The link should look like:
   ``` * Running on local URL:  http://127.0.0.1:7860 ```
4. The customer speaks first. Type your 'spoken' replies as the employee.
5. __Optional__ Use the **Reset Conversation** button to start a new session with a new randomly-selected scenario.



   
