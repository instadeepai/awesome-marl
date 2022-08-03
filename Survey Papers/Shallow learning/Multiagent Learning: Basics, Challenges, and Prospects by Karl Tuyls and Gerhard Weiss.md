# Multiagent Learning: Basics, Challenges, and Prospect

[ [Paper](http://www.weiss-gerhard.info/publications/AI_MAGAZINE_2012_TuylsWeiss.pdf) ]

> The purpose of this article is to introduce the basics of multi-agent learning while sketching its history and defining the most important developments and the foundations of MAL. To identify the main challenges the MAL field needs to tackle. And to announce promising future research directions in which the authors believe the field needs to develop.
> 

# The Nature of MAL:

<aside>
🖊️ “While we define the multiagent learning problem here as a learning problem with a number of complex factors, not so often researchers tackle the multiagent learning problem in a situation combining all of these factors. There have been many attempts to characterize and refine the goals and purposes of MAL, resulting in various taxonomies and classifications of MAL techniques”

</aside>


⇒ In this section, the authors cited different ways to distinguish between MAL learning and nature

### **Cooperative learning and Competitive learning**

1. **Cooperative learning:** 
    - The agents have the same reward function and the agents’ learning goal is to maximize their utility as a group
2. **Competitive learning:**
    - **T**he agents have individual reward functions and each of them is selfish in that it aims at maximizing its own utility even if this is only possible at the cost of the other agents and their individual utilities.

→ According to the authors, the cooperative-competitive distinction is not sharp with regard to the behavior of agents: a cooperative agent may encounter a situation in which it has to behave temporarily in a selfish way (while all involved agents have the same goal and are willing to cooperate, they may want to achieve their common goal in different ways); and a competitive agent may encounter a situation in which a temporary coalition with its opponent is the best way to achieve its own goal.

### Awareness degree of the other agents

- In this standard classification, we talk about the degree of awareness that is included in a range from **Fully unaware** to **Fully aware**
- This classification is related to the agents’ learning goals where some learning goals can be achievable with no or little awareness etc.

### The degree of homogeneity of the agents’ learning algorithm

- The homogeneity of the agents themselves, and the prior knowledge a learning agent has about the task, the environment, and the other agents.

### Model-based and model-free

- It is around having or learning a model of the environment dynamics and/or an opponent model predicting the behavior of other agents.

### Based on available MAL literature

→This classification is based on the possible goals of MAL research which were divided into 5 types.

1. **Computational MAL techniques**
2. **Descriptive MAL techniques**
3. **Normative MAL techniques**
4. **Cooperative MAL techniques**
5. **Noncooperative MAL techniques**

# A history perspective:

→ The development of the MAL field can roughly be divided into two periods.

### The startup Period (1980, 2000)

- At the end of this startup phase, the first general understanding of the role of learning in multiagent settings emerged.

### The consolidation Period

- A depth-first exploration characterized by a focus on certain multiagent learning techniques (especially reinforcement learning in a game-theoretic context) and on theoretical foundations of MAL.

# Challenges in Multiagent Learning:

### Classification limitation:

<aside>
🖊️ “This search is important because significant and continuing progress in a research field can only be expected if it is clear what the research should be about.”

</aside>


- The authors define 3 types of MAL:
    1. **Multiplied learning:** Several agents learn independently of one another; they may interact but their interactions do not change the way the individual agents learn.
    2. **Divided learning:**  An agent acts as a “specialist,” being responsible for a specific part of an overall learning process.
    3. **Interactive learning:**  The agents are engaged in a single learning process that becomes possible through a shared understanding of the learning task and goal.
- According to the authors, in contrast, interactive learning has largely been neglected and plays only a marginal role in current MAL research.

### MAL in complex systems:

<aside>
🖊️ “The field of MAL has often dealt with rather simple applications, usually in toy-world scenarios or drawn from game theory and mostly with only a few (typically two) learning agents involved.”

</aside>


- The simplification makes sense and is helpful for getting a better understanding of principle possibilities, limitations, and challenges of MAL in general and of specific MAL techniques in particular, but it is not sufficient.
- The MAL field needs to focus more than it currently does on complex and more realistic applications:
    - Eventually, this is the only way to find out whether and to what extent MAL can fulfill the expectations in its benefits
    - this is the best way to stimulate new ideas and MAL research directions that otherwise would not be explored.
- Real-life applications domains for MAL:
    - Ground and air traffic control
    - Distributed surveillance
    - Electronic markets
    - Robotic rescue
    - Robotic soccer
    - Electric power networks

# Conclusion

- In order to overcome some of the current issues through this article, we are convinced the field should take a broader and more interdisciplinary approach to MAL, which is an important step toward efficient multiagent learning in complex applications.
- Extending the scope needs to be done by building on the experience of the past 25 years and by drawing explicit connections between the different paradigms in order to tackle more complex problems.
- This search is important because significant and continuing progress in a research field can only be expected if it is clear what the research should be about.

- There has been substantial growth in the field of Multi-Agent Reinforcemnt Learning (MARL) in recent years. MARL covers a wide variety of problem fields which are constantly in a state of flux.
- This is a collection of review papers for MARL and evaluation methods for RL in general. We sort papers by publication date and survey subtopic. Any additions to this repo are welcome. Although our current focus is more on evaluation, this repository aims to include all relevant subtopics related to MARL.
