# Udacity-CarND-PID-Control
A PID controller for steering a vehicle, for the Udacity Self-Driving Car Engineer Nanodegree.

A PID (Proportional Integral Derivative) controller is a control loop feedback mechanism that is widely used in machines such as robots and vehicles. PID control is used to bring an actual characteristic (speed, pressure, etc) to the desired value in the optimum way, minimizing delay or overshoot. 

An example of PID control at work is cruise control, where the vehicle speed is kept at constant speed despite changing factors like the road gradient. In the diagram below by Control Notes, the set point is the defined cruise control speed, and the process variable is the vehicle speed observed by the odometer. The error is the difference between these 2 values.

<img src='https://github.com/leeping-ng/Udacity-CarND-PID-Control/blob/master/PID-Controller.png'>

For this project, the PID controller is used to drive a simulated car around a virtual track. The cross track error (CTE), which is the distance of the car from the middle of the road, is provided to the PID controller. The PID controller outputs a steering angle that will bring the car towards the middle of the road, minimizing the CTE.

**P (Proportional)**: Increasing the proportional gain (Kp) will improve the response time, but there will be more overshoot. For this project, if the Kp is too high, the car will oscillate wildly about the middle. If Kp is too low, the car will not react in time to sharp curves, and go off the road.

**I (Integral)**: The integral term is used to tackle systematic errors in the system, for example, if the car tyres are not aligned properly, it will have a natural tendency to drift to one side. Increasing the integral gain (Ki) will reduce the chances of the car drifting to one side.

**D (Derivative)**: The derivative term helps with damping and reduction of oscillations. Increasing the derivative gain (Kd) helps to dampen the oscillations and make the ride more smooth.

I started with the hyperparameters Kp=0.2, Ki=0.004, Kd=3.0 which were provided in the lesson, and found that they worked really well. I tried adjusting these values by changing one, and keeping the other two constant. After some trial and error, and running in the simulator, I determined that this set of gains were a good compromise between stable driving and tackling sharp corners.
