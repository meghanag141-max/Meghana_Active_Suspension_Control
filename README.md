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

The controlled system showed significant improvement compared to the uncontrolled system.

Improvements Achieved

- Reduced settling time
- Reduced oscillations
- Improved damping behavior
- Enhanced system stability


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

"Road Disturbance Response" (Images/road_disturbance_response.png)

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


Team Members

- Meghana G 
- Nagamani C N


Hackathon Submission

This project was developed as part of the CONTROL CRAFT HACKATHON.
