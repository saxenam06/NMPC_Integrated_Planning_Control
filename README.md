# Integrated Path Planning and Control for Lane Tracking together with Moving Obstacle avoidance using CASADI


In this repository, I explain the approach for  “Integration of Path Planning and Control to achieve the objective of tracking given Lane Waypoints together with Collision avoidance of the surrounding Static & Moving Obstacles” using CASADI. I used the main ideas of fusing of Moving obstacle states, Vehicle Dynamic model, objective function, and vehicle dynamic rollover safety constraints in the NMPC formulation from A.B. Dudekula [1] where the objective was to determine optimum Integrated path planning and control for Unstructured Off-Road environments. The objective of my work is to apply similar ideas but which are relevant to determine optimum Integrated Path Planning for Moving obstacle avoidance and Tracking of the given Lane waypoints for Autonomous navigation in the Highway Structured environment. Due to altogether a different application, the code given in the thesis was almost completely modified, all the relevant parameters were retuned, and the various components of NMPC were reconstructed and implemented in a different manner to achieve the objective desired here. I sincerely thank to the author of the thesis for open sourcing the code together with the thesis which helped me to understand how to formulate and implement various components of NMPC and therefore helped me to achieve my objectives here. 

# PROBLEM FORMULATION: Moving Obstacle Avoidance & Tracking of the given Lane Waypoints

We have the below scenario for our control objective i.e. Tracking of the given Waypoints of the Lane in magenta which is the current preferred lane of the ego vehicle, avoiding collision with the surrounding stationary (Road boundaries in Black) & moving obstacles (in Blue) and reaching the given goal location. The basic sketch for our problem is shown below. 
  ![image](https://user-images.githubusercontent.com/83720464/131503635-fa0fbeb3-4ae0-4134-8236-262a333424ae.png)

Important aspects of the Vehicle Dynamic model of ego vehicle and moving obstacles, integration of Moving obstacle states with ego vehicle states, evaluation of vertical load on each wheel considering lateral and longitudinal weight transfer for wheel lift-off rollover safety constraints, objective function and constraints. 
# Results
In the below video we see the results of our implementation. We see the planned path by the ego vehicle in green while tracking the reference lane waypoints in magenta and avoiding both road boundaries and moving obstacle in black and blue respectively. 

![131518775-6bda507d-4714-4e37-9b1d-acc6928d6b2f](https://user-images.githubusercontent.com/83720464/133928900-02ad03b5-16df-4b84-8c6e-08cefbe1f502.gif)

In below Fig. we see the results of all the important states and the control variables. We can see that the constraints on all the states and control variables were well respected by our NMPC implementation. 

![image](https://user-images.githubusercontent.com/83720464/131503882-38c0f146-831a-451b-956a-5e3479b0764a.png)

  
# REFERENCES
1.	A.B. Dudekula, Sensor fusion and Non-linear NMPC controller development studies for Intelligent Autonomous vehicular systems, Thesis 
2.	Reza N. Jazar, Advanced Vehicle Dynamics, Springer Book. 

