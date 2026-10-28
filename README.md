# EXPERIMENT: 1

## Representation of a Real-World Problem as a Markov Decision Process (MDP)

### Title: Smart Robot Vacuum Cleaner Using MDP

### 1. Aim

To implement a Smart Robot Vacuum Cleaner using a Markov Decision Process (MDP) to make decisions based on room cleanliness and battery level.

### 2. Problem Statement

A robot vacuum cleaner automatically cleans a room. It must decide whether to clean, move to another location, or recharge its battery based on its current condition.

Using MDP, the robot can make decisions to maximize cleaning efficiency.

### 3. MDP Components

| Component       | Description                            |
| --------------- | -------------------------------------- |
| States (S)      | Clean, Dirty, Low Battery              |
| Actions (A)     | Clean, Move, Recharge                  |
| Transition (P)  | Probability of moving to another state |
| Reward (R)      | Reward received after an action        |
| Discount Factor | 0.9                                    |

### 4. Reward Function

| Condition    | Reward |
| ------------ | ------ |
| Room Cleaned | +10    |
| Moving       | -1     |
| Low Battery  | -5     |
| Recharging   | +5     |

### 5. Algorithm

1. Start the program.
2. Initialize the robot states and actions.
3. Define transition probabilities.
4. Assign rewards to each state.
5. Select the current state.
6. Choose an appropriate action.
7. Calculate the next state and reward.
8. Display the result.
9. Stop.

### 6. Python Program

```
import randomprint("SMART ROBOT VACUUM CLEANER USING MDP")
print("------------------------------------")
# Statesstates = ["Clean", "Dirty", "Low Battery"]
# Actionsactions = ["Clean", "Move", "Recharge"]
# Discount factorgamma = 0.9
# Rewardsrewards = {    "Clean": 10,    "Dirty": -1,    "Low Battery": -5}
# Transition probabilitiestransitions = {    "Dirty": {        "Clean": [0.8, 0.1, 0.1],        "Move": [0.2, 0.6, 0.2],        "Recharge": [0.1, 0.7, 0.2]    },    "Clean": {        "Clean": [0.7, 0.2, 0.1],        "Move": [0.3, 0.6, 0.1],        "Recharge": [0.8, 0.1, 0.1]    },    "Low Battery": {        "Clean": [0.1, 0.2, 0.7],        "Move": [0.1, 0.1, 0.8],        "Recharge": [0.7, 0.2, 0.1]    }}
# Current statecurrent_state = "Dirty"
# Select actionaction = "Clean"# Determine next staterandom.seed(1)next_state = random.choices(    states,    weights=transitions[current_state][action],    k=1)[0]
# Calculate rewardreward = rewards[next_state]
# Display resultsprint("Current State:", current_state)
print("Selected Action:", action)
print("Next State:", next_state)
print("Reward:", reward)
print("Discount Factor:", gamma)
print("MDP Simulation Completed Successfully!")
```

### 7. Output

```
SMART ROBOT VACUUM CLEANER USING MDP
------------------------------------
Current State: Dirty
Selected Action: Clean
Next State: Clean
Reward: 10
Discount Factor: 0.9
MDP Simulation Completed Successfully!
```

### 8. MDP State Diagram

Dirty Room

Action: Clean

Transition probability

0.8

Clean

Reward +10

0.1

Dirty

Reward -1

0.1

Low Battery

Reward -5

### 9. Result

Thus, the Smart Robot Vacuum Cleaner was successfully represented using a Markov Decision Process. The robot's states, actions, transition probabilities, and rewards were defined and simulated using Python.

Note: This is a simplified MDP simulation using a predefined action. An optimal cleaning policy can be developed using Value Iteration or Policy Iteration.
