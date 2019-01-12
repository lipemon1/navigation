# Navigation Project Report

## First learn more about me...
Hi, thank you for reading my report. My name is Ramon Ferreira, I am a brasilian game developer that always used Unity but my knowledge on machine learning was zero until this course. So, for me it was very, very, very hard to understand all the concepts and what to do with which one of them. Now, I now that I should had started with a more initial course than this. But I'm glad that I'm here. Trying to make something with those lines of codes.
***
## Learning Algorithm
I'm gonna first tell what was my pipeline and then comment on my final structure.
First I started trying to understand the Agent and Model classes from Deep Reinforcement Learning Nanodegree **Deep Q-Networks**. If you have access to the course you can check it out, it's the second class workspace. As I never used python for work I have some serious trouble to understand every line. So I started copying the whole class e messing around the parameters.

After I made it work I started to looking for ways to use Double Deep Q-Networks, Dueling and Experienced Replay. First I read the articles suggested during the classes. When I finished my mind was half blowed because it was so cool and the other half because I didn't understand all of it. So I started to look for other people that made the same course and found one guy that literally showed me the path to light.

Man, you are the best.

Here it's solution repository for the same challenge.

After using some parts of this guy I could make the replay buffer work properly, the same for Double Deep Q-Networks and Dueling agents. Really, this guy is like a Angel.

This was my journey over the code in a brief but now, let's go to the beautiful part. How my final structure is working.
***
## Rewards. Hell Yeah!
### Configuration used for trainning
This is the types of algorithms used during trainning:
- Standard Deep Q-Network (Standard)
- Standard Deep Q-Network + Double (DDQN)
- Standard Deep Q-Network + Dueling (DQN + Dueling)
- Standard Deep Q-Netowrk + Dueling + Double (DDQN + Dueling)

I used **8 different agents configurations** as you can see on the image below.

![Agents Configuration](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agents-configuration.PNG)

Other configurations for the Deep Q-Network method was **the same for every agent.** Like those:
EPS Start = 1
EPS End = 0.02
Episodes for trainning = 1000
Episodes for test the saved agent = 10

Other configuration inside **Agent class**:
replay buffer size = int(1e5)
Minibatch size = 64
Discount factor = 0.99
Leraning rate = 5e-4

Here we can see the result for each agent trainned and tested.

### Agents Results
**Agent V1**

Configuration
![Alt Text][agentV1Setup].
[agentV1Setup]: images/agentV1setup.png "Agent V1 Configuration"

Training Plot

Results
![Alt Text][agentV1Result].
[agentV1Result]: https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV1result.PNG "Agent V1 Results"

Result Plot

This agent was the worst in Test mode after trainning.

**Agent V2**

Configuration
![Alt Text][agentV2Setup].
[agentV2Setup]: images/agentV2setup.png "Agent V2 Configuration"

Training Plot

Results
![Alt Text][agentV2Result].
[agentV2Result]: images/agentV2result.png "Agent V2 Results"

Result Plot

This agent was fastest one to beat the goal.

**Agent V3**

Configuration
![Alt Text][agentV3setup].
[agentV3setup]: images/agentV3setup.png "Agent V3 Configuration"

Training Plot

Results
![Alt Text][agentV3Result].
[agentV3Result]: images/agentV3Result.png "Agent V3 Results"

Result Plot

This agent has the best average in Test mode after trainning.

**Agent V4**

Configuration
![Alt Text][agentV4setup].
[agentV4setup]: images/agentV4setup.png "Agent V4 Configuration"

Training Plot

Results
![Alt Text][agentV4Result].
[agentV4Result]: images/agentV4Result.png "Agent V4 Results"

Result Plot

This agent has the worst average in Trainning mode.

**Agent V5**

Configuration
![Alt Text][agentV5setup].
[agentV5setup]: images/agentV5setup.png "Agent V5 Configuration"

Training Plot

Results
![Alt Text][agentV5Result].
[agentV5Result]: images/agentV5Result.png "Agent V5 Results"

Result Plot

This agent was to slowest to beat the goal.

**Agent V6** - Best average in Trainning mode

Configuration
![Alt Text][agentV6setup].
[agentV6setup]: images/agentV6setup.png "Agent V6 Configuration"

Training Plot

Results
![Alt Text][agentV6Result].
[agentV6Result]: images/agentV6Result.png "Agent V6 Results"

Result Plot

This agent has the best average in Trainning mode.

**Agent V7**

Configuration
![Alt Text][agentV7setup].
[agentV7setup]: images/agentV7setup.png "Agent V7 Configuration"

Training Plot

Results
![Alt Text][agentV7Result].
[agentV7Result]: images/agentV7Result.png "Agent V7 Results"

Result Plot

**Agent V8**

Configuration
![Alt Text][agentV8setup].
[agentV8setup]: images/agentV8setup.png "Agent V8 Configuration"

Training Plot

Results
![Alt Text][agentV8Result].
[agentV8Result]: images/agentV8Result.png "Agent V8 Results"

Result Plot

**Final conclusions**
Getting all the agents together we can make some very nice conclusions.

![Alt Text][agentsResult].
[agentsResult]: images/agents-configuration-result.png "Title"

For example:
    - All the agents that used EPS Decay = 0.95 were faster to get to the goal of 13.00 as score average.
    - The agent with the best average during training was different from the agent with best average during testing.
***
### Today we go for bananas, tomorrow for the world!
After seeing the result and make some conclusions of course there're space to improve the whole algorithm. Here is the list with some modification I want to make as soon as possible.
 - **More average score.** If you check my results you will find that my best agent could only mantain a average of 18.157. So one of the modifications is to change the learning algorithm so the agents can make more than that.
 - **Learn from pixels.** After I finish all the projects I want to go back here and make it learn from pixels. I'll be happier than Link from Zelda breaking pots on strange houses if I could make it work.
 - **Messing around with experienced replay.** I want to change more the experienced replay implemented to see if I can get different results. As I was following a done implementation I don't focus on changing a lot of aspects on this part. It could be a start to achieve more score.

