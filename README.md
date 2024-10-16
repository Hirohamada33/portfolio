# Portfolio

Hello ^^ <br> 
You've found me! <br> 
Welcome to my humble Git page. <br> 
Would you mind me to introduce you some projects I am so passionate about? <br><br> 

Lists of projects I have acheived: <br>
- [Sokoban puzzle solver](#sokoban-puzzle-solver) <br> 
- [Cartpole problem](#cartpole-problem)<br>
- [CPU design](#cpu-design)<br> 
- [Firefighter Bot](#firefighter-bot)<br>
- [Handheld educational assisting device](#handheld-educational-assisting-device) <br>
- [Hiking rescue model](#hiking-rescue-model) <br>
- [Image classifier](#image-classifier) <br>
- [Ranger project](#ranger-project) <br>

<br>
<br>
<br>
<br>



### Sokoban puzzle solver
The goal for a Sokoban puzzle, is that the player will have to push all the boxes into the pits to win the level. <br> 
This project aimed to solve the Sokoban puzzle using classical artificial intelligence approach - search algorithm. 
In addition to the traditional Sokoban puzzle, the problem introduce **weights** for which each box may labelled with a weight hence each movement of this box will need to add the effect of the weight in the action cost. The goal of the game is to minimise the action cost.  

In detail, the search algorithm used is **astar graph search**. Based on the nature of the game, the player (or agent) have the information of the boxes and pits, hence making this an **informed search**. It is possible to go back to a state (i.e., have the same layouts / positions of all objects), hence **graph search** is more suitable than a **tree search**. Finally detail is that, a heuristic method is used along with priority queue in the astar search. The formula is given by shortest cost (path + weight) of each box to each pit (1 to 1 relation) + the path of the player to a nearest box (the distance is L1 - Manhattan distance).  <br><br>
Below is a demonstraction of the astar graph search agent. 

https://github.com/user-attachments/assets/abcc2545-0b7c-4138-9d36-c5f2845bd630


<br>
<br>
<br>
<br>



### Cartpole problem
This is a classical reinforcement learning problem. The cart can choose from the actions of left or right. For each state / timeframe, if the pole is still "being balanced" (i.e., non-terminal or truncated states) then agent receive a reward of +1. The agent also additionally receieve a reward at terminal or truncated state.
The goal of the game is try to balance the pole as long as possible. <br>
The approach here is to use tabular form of **Monte-Carlo back up** of the state-action pair values. 

Below is the agent at the early stage of the learning process. As can be seen due to the lack of learning experience, the game reaches terminal or truncated states very soon. 

https://github.com/user-attachments/assets/122070df-d0b3-40b6-90e1-e3ac65477c86

<br><br>

As the time elapsed, the state-action pairs got updated and the policy got improved. 


https://github.com/user-attachments/assets/98480be4-7c26-4b34-85da-365e7c9c929c






### CPU design
Starting from a module we explored the construction of cellular automation within Matlab. This is a first time I was introduced to Conway's Game of Life. <br> 
While fasinated by the patterns and constructions such as glider guns, spaceship, eater etc, soon after I discovered Game of Life is proven to be Turing Complete. Where my journey of Computer Architecture begins. <br>
Below is my first attempt to construct logic gates in Game of Life. (In fact, it is a 8-bit adder - parallel data output, ripple adder, with delays introduced by traversal of gliders) 



https://github.com/user-attachments/assets/c6c94eb6-0994-40cb-8adb-2888d4432b50

<br><br>
Further on I realised Game of Life has some natural limitations of constructing a computer, including difficulties in wire crossover (there's no layer, only 2D!), criticality in position and timing (phases and periodicity matters significantly in Game of Life), as well as the maintainabiity and readability of gates. Hence I switched to a different platform "Turing Complete" logic simulator.  

<br> 
This is a project I've accomplished in a game simulator "Turing Complete". The game provides logic gates simulation and timing signal, as well as comprehensive tutorials and challenges to learn from.<br>
Below is a design I created. 
<img width="960" alt="wire spaghetti" src="https://github.com/user-attachments/assets/afb8992b-2b3e-4767-b98c-ceeed47cdb2f">
<br>
<br>
In the game I tried to write some assembly to complete some challenges in the game. Below is the machine doing a bubble swap of a series of data stored in RAM. 
<br>

https://github.com/user-attachments/assets/5802d643-a07a-4757-a8e1-9934f66427cb

<br>
<br> 

Besides the CPU, I also experimented with making some components. 

Systolic array:
<img width="645" alt="截圖 2024-10-15 下午9 48 03" src="https://github.com/user-attachments/assets/3b7487ea-59a6-476c-93c8-9fd561340f73">

<br>
<br>

Pipelined machine (a confession: the architecture of this machine is still **single-cycled** due to the design assumption of the game.) 
<img width="1361" alt="截圖 2024-10-15 下午9 47 08" src="https://github.com/user-attachments/assets/501e5103-b2f2-4683-96f2-53c39c393065">

<br>
<br> 
Register files <br>
(I choose the number of 30 regs just because I can) <br>
<img width="964" alt="截圖 2024-10-15 下午9 49 01" src="https://github.com/user-attachments/assets/08e31686-2f51-41e7-8619-213bd777f439">


### Firefighter bot
This is a group project I participated in 2023, University Microcontroller Hackathon. The theme is "Autonomous system". <br> 
![342974716_771810660952375_7269678421067040297_n](https://github.com/user-attachments/assets/93d24796-000d-4b5b-adf0-ab9a7e1fbed0)
<br>
The firefighter bot is equipped with two IR sensors, a fan and a small camera. Two microcontrollers are used - Arduino and ESP32, one for the camera data handling and the other one for main program control. Between the two microcontrollers the UART protocol was used, sending the information of the fire source, including height, width, location and number of fire source. <br>
Once a fire has been detected, the firefighter bot will drive towards the fire source, and as getting closer to the fire source IR readings are used to assist the identification of exact location. A fan is controlled by the relay, once close enough to the fire source, it will turn on and distinguish the fire. (A confession: we considered the fact that not all the fire sources are suitable to use wind to dinstiguish. Our initial idea is to release carbon dioxide from a compressed capsule, however was found too difficult to achieve within the short period of time.<br>
In the group I was in charged of camera detection. We were initially trying to use machine learning, however by the time the knowledge is beyond the understanding, hence the simplest colour thresholding is used. <br>
Below is the demonstration of the firefighter bot distinguishing a fire in a candle. 
<br> 


https://github.com/user-attachments/assets/f11e5c70-1adc-4d61-a27b-47c3893fbf4e

<br>





### Handheld educational assisting device
This is a group project I participated in 2024, University Microcontroller Hackathon. The theme is "Education and Innovation". <br> 
Unfortunately I forgot to keep the visual record for this device :( <br>




### Hiking rescue model
A simple rescue model that uses random walk to statiscally predict the final location of a lost hiker. <br> 
Using colour thresholding and masking to generate height data from topological map, then setting for each height the expected length of step / speed of travel to be different based on the height of the person current location (the assumption here is, the speed of travel is proportional to how low the elavation is, i.e., the higher it is, the slower the person walk) <br>
Below is an example of a random walk from Australia coastline, around Brisbane. <br>
<img width="524" alt="截圖 2024-10-14 下午6 30 22" src="https://github.com/user-attachments/assets/c45b6754-6d93-4b72-8153-2bbddefee9d4">
<br>
Based on the final location of each particle, a 3D-histogram can be generated to sum up the possibility of finding the person in the specific region, represented by the height of the histogram. Thus this can be used to list the priority of searching in a time-critical situation. 
<br>
<img width="547" alt="截圖 2024-10-14 下午6 30 36" src="https://github.com/user-attachments/assets/67602c94-8096-4059-afa3-cc49fe9179ff">
<br>
However, a confession is that this rescue model was created within the first year university, its 

### Image classifier
A group assignment for image classifier using neural network. The Keras module is used, the technique is **transfer learning**. We build a few layers on top of trained weights from ImageNet, the goal is to classify 5 classes of flowers - daisy, dandelion, roses, sunflowers and tulips. <br> 
Below is the key summary of the result: 
<br>
<img width="461" alt="截圖 2024-10-16 下午3 32 37" src="https://github.com/user-attachments/assets/c880f147-d3a8-4c60-a9e9-b44d80f238f2">
<img width="599" alt="截圖 2024-10-16 下午3 33 54" src="https://github.com/user-attachments/assets/a4605d77-95e9-47a2-abb3-5e136b3d2778">

<br>

Some of the key learnings from this project are the tuning and experimentation of **hyperparameter evaluation (learning rates, momentum and Nesterov momentum)** and **value of K in K fold validation**. 


### Ranger project 
This is a group assignment that we were to build a ranger car that drives autonomously and follow a certain task, including line-following, detecting the curvature signs and adjust speed if necessary, detecting the slow zone (marked red for start and green for end of the slow zone) and alternate routes every time in the slow zone, and finally show indicative LEDs for each circumstances (Red for stopping, Green for detection of straight line (i.e., error of sensors has been relatively small for a period of time), Blue for inside the slow zone)<br>
Within the group I am the software lead, who is in charge of writing the main program for the ranger project. I also helped design the PCB for the mainboard. <br> 

![IMG_0716](https://github.com/user-attachments/assets/29c85586-9e44-4aee-9402-c6868bc42f3b)

Below is the schematic of the PCB I designed for the main board (although my teammate has a better alternative). 
<img width="988" alt="截圖 2024-10-16 下午10 15 50" src="https://github.com/user-attachments/assets/266fed3a-a49a-4480-bcde-70f129622eb3">

<img width="994" alt="截圖 2024-10-16 下午10 18 35" src="https://github.com/user-attachments/assets/f5b0e952-26a8-465e-8397-7dd5e200b4fc">


Below is the demonstration of the operation of the ranger. 

https://github.com/user-attachments/assets/9d6f4358-330f-4a60-9a39-090f86cbcba9




