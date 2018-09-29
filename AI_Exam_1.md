# AI Exam One

## Key Agent Terms  

**Performance Measure**  
If an agent performs a sequence that is desirable, then the agent has performed well. This notation of desirability is captured by a *performance measure* that evaluates any given sequence of environment states.  

**Actuators**  
The actuators for an automated taxi are:  

* control over engine through the accelerator
* conttol over the steering and breaking  

**Sensors**  
The basic sensors for the taxi are

* video cameras  
* infrared or sonar sensors to detect distance from other cars  

## Key Environment Terms  

### Deterministic vs Stochastic

**Deterministic**  
environments where any action taken influences its outcome, In chess if you move a pawn from A3 to A5 it will always work (there is no uncertainty).  
**Stochastic**  
environments have a level of uncertaint (any game that involves dice, or a taxi driving), you can never be certain of the number that will be rolled.

### Fully Observable vs Partially Observable

**Fully Observable**  
Agent's sensors give it access to the complete state of the environment at each point in time  
**Partially Observable**  
An environment might be partially observable because fo noisy and inaccurate sensors or because parts of the state are simply missing from the data sensors  

### Episodic vs Sequential

**Episodic**  
an agent's experience is divided into atomic episodes, in each episode the agent receives a percept and then performs a single action. *the next episode does not depend on the actions taken in previous episodes*. (determining if an item on an assembly line is defective)  
**Sequential**  
All current decisions could affect all future decisions (chess and taxi driving)

### Static vs Dynamic

**Static**  
If an environment doesn't change  
**Dynamic**  
If an environment can change while an agent is deliberating  
**Semidynamic**  
If the environment itself doesn't change with passage of time but the agent's performance score does, then we say the environment is *semidynamic*

### Discrete vs Continuous

**Discrete**  
Chess has a finite number of distinct states in its environment that can drive the final outcome of a task.  
**Continuous**  
Taxi-driving is a continuous-state and continuous-time problem. It relys on an unknown and rapidly changing data source.  

### Known and Unknown

**Known**  
In a known environment, the outcomes for all actions are given  
*it is possible for a known environment to be partially observable (solitare card game, you know the rules but unable to see the cards that have not been turned over)*  
**Unknown**  
The agent will have to learn how the eviornment works in order to make a good decision.  
*you can be fully observable - in a video game, the screen may show the entire game state but I still don't know what the buttons do until I try them*

## Graphs

### BDF (Breath Depth Search)  

The *shallowest* unexpanded node is chosen for expansion. An appropriate data structrue for the *frontier* would be a *queue*.

### Uniform-Cost Search  

Uniform-Cost Search expands the node with the *lowest path cost*. This is done by storing the frontier as a priority queue.  
*differences between Uniform-Cost Search and BDF*

* the goal test is applied to a node when it is *selected for expansion*, rather than when it is first generated because the first goal node that is generated might be on a suboptimal path.
* Another test is added in case a better path is found to a node currently on the frontier

### Informed (Heuristic) Search Strategies  

This uses problem-specific knowledge beyond the definition of the problem itself. This will find solutions more efficiently than an uninformed strategy.

#### Heuristic Function

*h(n)* estimated cost of the cheapest path from the state at node n to a goal state.

#### Greedy Best-First Search

Greedy uses the **straight line distance** heuristic. You need to know the straight line distance from each node to the goal node.  

Greedy will find a solution without ever expanding a node that is not on the solution path; hence, its search cost is minimal. However the Greedy search will not find the most optimal solution (it just tries to get as close to the goal as it can).

![Heuristics](/Users/ajwoo/Desktop/AI_Exam1_Notes/screenshots/heuristics.png)

![Greedy](/Users/ajwoo/Desktop/AI_Exam1_Notes/screenshots/Greedy.png)

#### A* Search

A\* evaluates each node by combining the cost to reach the node you are trying to expand to and the heuristic.

![Map](/Users/ajwoo/Desktop/AI_Exam1_Notes/screenshots/map.png)

![Heuristics](/Users/ajwoo/Desktop/AI_Exam1_Notes/screenshots/heuristics.png)

![AStar](/Users/ajwoo/Desktop/AI_Exam1_Notes/screenshots/A*.png)