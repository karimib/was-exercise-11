# WAS Exercise 11 - Reinforcement Learning Agents

## Link to GitHub Repository
<https://github.com/karimib/was-exercise-11>

## Task 1

The goal of this task is to design the states, actions and rewards for the model.
From a technical perspective the agents aim to fulfill the goal named task_requirement
that contains two constant values x1, x2 where x1 stands for the rank of illuminance that zone1 requests
and x2 stands for the rank of illuminance that zone2 requests. The goal is fulfilled if the observed indoor
illuminance level in each zone corresponds to the ranks illuminance interval.

### States

First we define the states that are required to indicate if these goals have been fulfilled or not, so
the first intuition leads to two states s1 and s2 where s1 indicates that the goal has not been fulfilled
and s2 that indicates that the goal has been filfilled. Now since we have two zones that define goals to be fulfilled
we extend the states by 4 more states, where s3 indicates if the goal for zone 1 has been fulfilled and s4 that indicates that the goal for zone1 has not been fulfilled
and equally s5 and s6 for zone2.

### Actions

In order to increase or decrease indoor illuminance the agents can turn on/off the ligths as well as raise/lower the blinds.
Therefore we define action a1 as turning on the lights and action a2 as turning off the lights.
Furthermore dwe define action a3 as raising the blinds and action a4 as lowering the blinds.
Each of these actions can be performed in zone1(a1-a4) as well as in zone2 (a5-a8).

### Rewards

Rewards are given when an action leads to a goal state or it increases the probability of reaching the goal state, therefore
rewards are defined as positive when they increse the probability to reach the goal state and negative when lowering the probability to reach the goal state.

## Task 2 - Pitfalls

### Implementation of the Q-Learning Algorithm

First I tought that the implementation of the Q-Learning Algorithm would be straightforward. But since it is dependent on the actual Lab state, i had to adapt it to
consider the context of the lab. Explicitly to get the applicable states and loop trough them until a terminal state has been reached. Fortunately the lab provides
some methods to get the applicable states where I could then check if the next state is really a valid state and if not the reward had to be set to a negative value.

