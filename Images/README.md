-> Open Loop Suspension Response

This graph shows the behavior of the suspension system without any controller. The response rises slowly and takes more time to stabilize, indicating poor damping characteristics. Since there is no active control, the suspension cannot quickly suppress vehicle vibrations caused by road disturbances. The graph demonstrates that the uncontrolled system has slower settling and reduced ride comfort. This highlights the need for an active suspension controller to improve vehicle stability and passenger comfort.


-> Closed Loop Response with PD Controller

This graph represents the suspension response after applying the PD controller. The system reaches stability much faster compared to the open-loop response. The proportional gain improves the response speed, while the derivative gain reduces oscillations and improves damping. The graph shows smoother stabilization and better vibration control. This proves that the PD controller significantly enhances suspension performance and ride comfort.


-> Comparison of Suspension Responses

This graph compares the uncontrolled suspension system with the PD-controlled suspension system. The uncontrolled response settles slowly, whereas the controlled response stabilizes much faster. The PD-controlled system reduces oscillations and achieves better damping characteristics. The comparison clearly demonstrates the effectiveness of feedback control in improving system stability. This graph is important because it visually proves the improvement achieved using the PD controller.


-> Response to Road Disturbance

This graph simulates the suspension response under road disturbances such as bumps and uneven surfaces. The sinusoidal disturbance represents continuous road vibrations experienced by a moving vehicle. The PD-controlled suspension effectively suppresses excessive oscillations and maintains smoother vehicle motion. The response remains stable even under varying disturbance conditions, showing good robustness of the controller. This demonstrates the ability of the active suspension system to improve ride quality on rough roads.

Advanced Road Condition Analysis
To evaluate the performance of the active suspension system, a PD controller was tested under different real-world road conditions. Each graph compares the controlled system (PD controller) with the uncontrolled system (passive suspension) under identical inputs.

-> Smooth Highway Road
This condition represents ideal driving on a smooth highway with minimal disturbances.
Uncontrolled system: Shows small but continuous oscillations due to natural vehicle dynamics.
Controlled system (PD): Effectively suppresses vibrations and stabilizes the response quickly.
Result: The PD controller improves ride comfort by reducing even minor vibrations.

-> Speed Breaker Condition
This condition simulates a sudden upward displacement caused by a speed breaker or road hump.
Uncontrolled system: Exhibits high overshoot and prolonged oscillations after impact.
Controlled system (PD): Reduces peak response and settles quickly.
Result: Improved stability and reduced shock impact on passengers.

-> Rough Road Condition
This condition represents continuously uneven road surfaces causing frequent disturbances.
Uncontrolled system: High-frequency and high-amplitude oscillations are observed.
Controlled system (PD): Significantly reduces vibration amplitude and smooths the response.
Result: Better damping performance under continuous disturbances.

-> Pothole Disturbance
This condition simulates a sudden downward displacement caused by potholes or road damage.
Uncontrolled system: Large dip followed by strong rebound oscillations.
Controlled system (PD): Reduces impact severity and quickly stabilizes motion.
Result: Improved shock absorption and reduced rebound effect.
