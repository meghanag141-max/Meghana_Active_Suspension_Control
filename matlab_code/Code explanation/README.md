Our code explains how an Active Suspension System improves vehicle stability and ride comfort using a PD Controller.

Simple Understanding of the Project
When a vehicle moves on:
bumps
potholes
rough roads
the vehicle body vibrates.

The purpose of suspension is to:
reduce vibrations
improve comfort
maintain stability
What our Code Actually Does

Our MATLAB code simulates:
1. Suspension System
This part:
represents the vehicle suspension mathematically.
It models:
spring
damper
vehicle body motion

2. Open-Loop System
This section:
MATLAB
step(G)
shows:
suspension WITHOUT controller
Meaning:
no intelligent control
more vibrations
slow stabilization
The graph explains:
how badly the vehicle behaves after a bump.

3. PD Controller
This part:
MATLAB
C = Kp + Kd*s;
creates the PD controller.
What PD Means
P → Proportional
Responds quickly to vibration.
D → Derivative
Reduces oscillations and improves damping.
Together they:
stabilize the vehicle faster
reduce body movement

4. Closed-Loop System
This line:
MATLAB
T = feedback(C*G,1);
creates the active suspension system.
Now:
output is continuously monitored
controller automatically corrects vibration
This is called:
Feedback Control System

5. Closed-Loop Response
This graph:
MATLAB
step(T)
shows:
suspension WITH controller
Expected result:
faster settling
less oscillation
smoother ride

6. Comparison Plot
This part:
MATLAB
step(G,'r',T,'b')
compares:
uncontrolled system
controlled system
This is the most important proof that: PD controller improved performance.

7. Road Disturbance Simulation
This part:
MATLAB
lsim(T,road_bump,t)
simulates:
rough road conditions
speed breakers
road vibrations
It checks whether the controller can handle disturbances.

8.Advanced Road Condition Analysis
To further evaluate the effectiveness of the active suspension system, the controller was tested under different real-world road disturbance conditions.

The following road profiles were simulated:

1. Smooth Highway Road
   Represents normal highway driving conditions with very small vibrations and smooth vehicle motion.

2. Speed Breaker Condition
   Simulates sudden elevation changes caused by speed breakers or road humps.

3. Rough Road Condition
   Represents uneven and continuously varying road surfaces that generate frequent vibrations.

4. Pothole Disturbance
   Simulates sudden downward impacts caused by potholes and damaged roads.

These additional simulations help analyze the robustness of the PD controller under varying disturbance conditions.

The results demonstrate that the active suspension system successfully:

- reduces excessive body vibrations
- improves damping behavior
- maintains better vehicle stability
- enhances passenger ride comfort

Smart Active Suspension Concept

Modern active suspension systems can be further improved using intelligent control techniques.

In future implementations:

- sensors can continuously monitor road conditions
- controller gains can automatically adjust in real time
- adaptive control can optimize suspension performance for different terrains

Such smart suspension systems are highly useful in:

- electric vehicles
- autonomous vehicles
- modern automotive safety systems

The current project provides a foundational model for developing intelligent active suspension control systems.

9. Performance Analysis
This part:
MATLAB
stepinfo(T)
calculates:
settling time
overshoot
peak response
rise time
These are standard control-system performance metrics.
