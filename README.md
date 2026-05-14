Active Suspension Control System Using PD Controller

Problem Statement

Design a control system to minimize vehicle vibrations caused by road disturbances.

The suspension system is represented by the transfer function:

G(s) = 1 / (s² + 3s + 2)

Objectives

- Minimize oscillations
- Improve damping behavior
- Achieve settling time less than 5 seconds
- Enhance ride comfort and vehicle stability


Project Overview

This project presents the design and simulation of an Active Suspension Control System using a PD Controller.

The system is analyzed under road disturbance conditions (step input), and the controlled response is compared with the uncontrolled response.

The proposed controller improves damping characteristics, reduces vibrations, and provides faster settling performance.


System Model

The suspension system transfer function is:

G(s) = 1 / (s² + 3s + 2)

Where:

- Input → Control Force
- Output → Vehicle Body Displacement
- Disturbance → Road Bump


Controller Design

A PD (Proportional-Derivative) controller is used to improve the dynamic response of the suspension system.

Controller Equation:

C(s) = Kp + Kd*s

Selected Controller Parameters:

- Kp = 15
- Kd = 8

Advantages of PD Controller

- Reduces oscillations
- Improves damping
- Faster stabilization
- Better ride comfort


Simulation and Analysis

The system was simulated using MATLAB

The following analyses were performed:

- Open-loop response analysis
- Closed-loop response analysis
- Step response comparison
- Performance evaluation

Performance Metrics

Open Loop System

- Rise Time: 2.5901 s
- Transient Time: 4.6002 s
- Settling Time: 4.6002 s
- Overshoot: 0 %
- Peak Value: 0.4996
- Peak Time: 7.7827 s

Closed Loop System

- Rise Time: 0.2462 s
- Transient Time: 0.4536 s
- Settling Time: 0.4536 s
- Overshoot: 0 %
- Peak Value: 0.8821
- Peak Time: 2.0103 s

Performance Improvement

- Settling Time Improved by 90.14%
- Vibrations were significantly reduced using the PD controller
- Damping behavior was improved
- Ride comfort and suspension stability were enhanced successfully

The simulation results confirm that the PD controller effectively improves the performance of the active suspension system under disturbance conditions. 


Project Structure

Active_Suspension_Control/

1. matlab_code/

2. images/

3. demo_video.mp4

4. README.md

Simulation Results

Open Loop Response

The open-loop response shows the behavior of the suspension system without any controller.

"Open Loop Response" https://raw.githubusercontent.com/meghanag141-max/Meghana_Active_Suspension_Control/refs/heads/main/Images/Open%20Loop%20Suspension%20Response.jpg


Closed Loop Response

The closed-loop response demonstrates improved damping and faster stabilization after applying the PD controller.

"Closed Loop Response" https://raw.githubusercontent.com/meghanag141-max/Meghana_Active_Suspension_Control/refs/heads/main/Images/Closed%20loop%20Response%20with%20PD%20Controller%20%20.jpg


Comparison of Responses

The comparison graph shows that the controlled system settles much faster than the uncontrolled system.

"Comparison Plot" https://raw.githubusercontent.com/meghanag141-max/Meghana_Active_Suspension_Control/refs/heads/main/Images/Comparison%20of%20Suspension%20Responses.jpg


Road Disturbance Response

The system exhibits improved vibration suppression under road disturbance conditions.

"Road Disturbance Response" https://raw.githubusercontent.com/meghanag141-max/Meghana_Active_Suspension_Control/refs/heads/main/Images/Response%20to%20Road%20Disturbance%20.jpg

Advanced Road Condition Analysis

To further evaluate the performance of the active suspension system, the PD controller was tested under different real-world road conditions.

Smooth Highway Road

Simulates smooth driving conditions with minimal road disturbances.
https://raw.githubusercontent.com/meghanag141-max/Meghana_Active_Suspension_Control/refs/heads/main/Images/Response%20under%20Smooth%20road%20conditions.jpg

Speed Breaker Condition

Represents sudden elevation changes caused by speed breakers or road humps.
https://raw.githubusercontent.com/meghanag141-max/Meghana_Active_Suspension_Control/refs/heads/main/Images/Responseunder%20spead%20breaker%20conditions.jpg

Rough Road Condition

Simulates uneven road surfaces that generate continuous vibrations.
https://raw.githubusercontent.com/meghanag141-max/Meghana_Active_Suspension_Control/refs/heads/main/Images/Responseunder%20rough%20road%20conditions.jpg

Pothole Disturbance

Represents sudden downward impacts caused by potholes and damaged roads.
https://raw.githubusercontent.com/meghanag141-max/Meghana_Active_Suspension_Control/refs/heads/main/Images/Responseunder%20pothhole%20conditions.jpg

The simulation results show that the PD controller effectively reduces vibrations and improves vehicle stability under different disturbance conditions.

Tools and Technologies Used

- MATLAB
- Control System Toolbox
- GitHub


Future Scope

Possible future improvements include:

- Adaptive suspension control
- AI-based controller tuning
- Real-time implementation
- Smart sensor integration


Conclusion

The designed PD controller successfully improved the performance of the active suspension system by reducing vibrations and enhancing damping characteristics.

The project demonstrates the effectiveness of control systems in improving ride comfort and vehicle stability under road disturbance conditions.

The simulation results confirm that the PD controller effectively improves damping behavior, reduces settling time, and enhances suspension system stability under disturbance conditions.

Demo Video

A demonstration video showing the MATLAB simulation and response analysis is included in this repository.

File: VID-20260513-WA0007.mp4

Team Members

- Meghana G 
- Nagamani C N


Hackathon Submission

This project was developed as part of the CONTROL CRAFT HACKATHON.
