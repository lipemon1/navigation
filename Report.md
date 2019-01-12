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
 - EPS Start = 1
 - EPS End = 0.02
 - Episodes for trainning = 1000
 - Episodes for test the saved agent = 10

Other configuration inside **Agent class**:
 - replay buffer size = int(1e5)
 - Minibatch size = 64
 - Discount factor = 0.99
 - Leraning rate = 5e-4

Here we can see the result for each agent trainned and tested.

### Agents Results
**Agent V1**

Configuration

![Agent V1Setup](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV1setup.PNG)

Training Plot HERE

Results

![Agent V1Result](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV1result.PNG)

Result Plot

This agent was the worst in Test mode after trainning.

**Agent V2**

Configuration

![Agent V2Setup](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV2setup.PNG)

Training Plot

Results

![Agent V2Result](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV2result.PNG)

Result Plot

This agent was fastest one to beat the goal.

**Agent V3**

Configuration

![Agent V3Setup](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV3setup.PNG)

Training Plot

Results

![Agent V3Result](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV3result.PNG)

Result Plot

This agent has the best average in Test mode after trainning.

**Agent V4**

Configuration

![Agent V4Setup](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV4setup.PNG)

Training Plot

Results

![Agent V4Result](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV4result.PNG)

Result Plot

This agent has the worst average in Trainning mode.

**Agent V5**

Configuration

![Agent V5Setup](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV5setup.PNG)

Training Plot

Results

![Agent V5Result](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV5result.PNG)

Result Plot

This agent was to slowest to beat the goal.

**Agent V6** - Best average in Trainning mode

Configuration

![Agent V6Setup](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV6setup.PNG)

Training Plot

Results

![Agent V6Result](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV6result.PNG)

Result Plot

This agent has the best average in Trainning mode.

**Agent V7**

Configuration

![Agent V7Setup](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV7setup.PNG)

Training Plot

Results

![Agent V7Result](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV7result.PNG)

Result Plot

**Agent V8**

Configuration

![Agent V8Setup](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV8setup.PNG)

Training Plot

Results

![Agent V8Result](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agentV8result.PNG)

Result Plot

**Final conclusions**
Getting all the agents together we can make some very nice conclusions.

![Agents Results](https://raw.githubusercontent.com/lipemon1/navigation/master/images/agents-configuration-result.png)

For example...
   - All the agents that used EPS Decay = 0.95 were faster to get to the goal of 13.00 as score average.
   - The agent with the best average during training was different from the agent with best average during testing.
***
### Today we go for bananas, tomorrow for the world!
After seeing the result and make some conclusions of course there're space to improve the whole algorithm. Here is the list with some modification I want to make as soon as possible.
 - **More average score.** If you check my results you will find that my best agent could only mantain a average of 18.157. So one of the modifications is to change the learning algorithm so the agents can make more than that.
 - **Learn from pixels.** After I finish all the projects I want to go back here and make it learn from pixels. I'll be happier than Link from Zelda breaking pots on strange houses if I could make it work.
 - **Messing around with experienced replay.** I want to change more the experienced replay implemented to see if I can get different results. As I was following a done implementation I don't focus on changing a lot of aspects on this part. It could be a start to achieve more score.

