# Home-Energy-Recommendation-System--HERS
Paper: Home Energy Recommendation System(HERS): A Deep Reinforcement Learning Method for Electricity Optimization in Smart Homes


1-Dependencies:
Numpy
Matplotlib
Pandas
Math
Random
Tensorflow 
Keras
Pytorch

2-Data Generation: 
	Throughout the code we have used
 padding=50; # non-informative addded characters to a string to the ends of it for formatting purposes.
 
	a)Activity Labels:

Activity labels are taken from the Activity Recognition with Ambient Sensing (ARAS) dataset. link:
https://www.cmpe.boun.edu.tr/aras/

	We extracted the 15-minute interval activity labels from the daily txt files provided in the dataset. 
This is implemented in house_B_activity_data.ipynb

	b) Device Operation Data:

We generated our device operation data from the activity labels as explained in the main paper.
This is implemented in smart_home_data.ipynb
	
 c) Results:
 
We implemented our proposed deep RL based Home Energy Recommendation System(HERS) in  HERS.ipynb

We applied the popular Advantage Actor Critic(A2c) algorithm. 

Hyperparameters are:
	GAMMA = 0.99
 
For the 4 devices; input states and output actions are taken as explained in the main paper. The network architectures are: (Hidden layers are shown as (number of neurons, activation function))

1. AC
Actor Model structure: (learning_rate=3e-6),    1 (input) -(12, linear)-(12, relu)-(2, softmax)
Critic Model structure: (learning_rate=3e-6),    1 (input) -(12, linear)-(12, relu)-(1, linear) 
	
2. DW
Actor Model structure: (learning_rate=3e-6),    18 (input) -(48, linear)-(120, linear)-(48, relu)-(18, softmax)
Critic Model structure: (learning_rate=3e-6),   18 (input) -(48, linear)-(120, linear)-(48, relu)-(18, linear)
	
3. WD
Actor Model structure: (learning_rate=3e-6),    18 (input) -(48, linear)-(120, linear)-(48, relu)-(18, softmax)
Critic Model structure: (learning_rate=3e-6),   18 (input) -(48, linear)-(120, linear)-(48, relu)-(18, linear)

4. EV
Actor Model structure: (learning_rate=3e-6),    3 (input) -(48, linear)-(120, linear)-(48, relu)-(5, softmax)
Critic Model structure: (learning_rate=3e-6),   3 (input) -(48, linear)-(120, linear)-(48, relu)-(5, linear)
	 
