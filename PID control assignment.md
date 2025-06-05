1.  **Ziegler-Nichols Method:**
	1. What were your determined values for $K_u$ and $T_u$?
		    $K_u = 400$  
		    $T_u = 0.1$
    2. Show your calculations for the initial $K_p, K_i, K_d$ values using the Ziegler-Nichols PID tuning formula.  
		    $K_p = 0.6 \cdot K_u = 240$  
			$K_i = \dfrac{2 \cdot K_p}{T_u} = \dfrac{2 \cdot 240}{0.1} = 4800$  
			$K_d = \dfrac{K_p \cdot T_u}{8} = \dfrac{240 \cdot 0.1}{8} = 3$

2.  **Impact of PID Terms:**
    1. Describe the effect of increasing $K_p$ (proportional gain) on the system response. How did it affect rise time, overshoot, and steady-state error?  
	    - **Rise time** decreases: A higher $K_p$ makes the controller more aggressive in correcting the error, allowing the system to reach the setpoint faster.  
	    - **Overshoot** increases: The aggressive correction can cause the system to exceed the target.  
	    - **Steady-state error** decreases: The system gets closer to the setpoint, although it may not fully eliminate the error. The curve often resembles $e^{-x}$.  
	    - With sufficiently high $K_p$, the system begins to oscillate.
	    
    2. Describe the effect of increasing $K_i$ (integral gain) on the system response. How did it affect steady-state error and oscillations?  
	    - Reduces **steady-state error** by integrating past errors and applying a correction based on accumulated error.  
	    - May **increase overshoot** and cause **oscillations**, due to delayed response and cumulative effect.

    3. Describe the effect of increasing $K_d$ (derivative gain) on the system response. How did it affect overshoot and settling time?  
	    - **Overshoot** decreases: The derivative term dampens the response by predicting the trend of error.  
	    - **Settling time** improves: The system stabilizes more quickly after reaching the target, reducing oscillations.

3.  **Performance Comparison:**
    1. Compare the system's performance (in terms of settling time, overshoot, and steady-state error) when using the Ziegler-Nichols initial parameters versus your fine-tuned parameters. Explain the differences you observed.  
		- Initially, I manually tuned $K_p$ to obtain a satisfactory result. However, using the Ziegler-Nichols method gave a much more refined tuning, with improved stability and a better balance between rise time and overshoot. Fine-tuning based on that further improved performance.

	2. Attach the plots for both the Ziegler-Nichols tuned system and your fine-tuned system.  
		- My fine-tuned system  
		![[Screenshot from 2025-06-05 09-11-32.png]]  
		- Ziegler-Nichols method  
		![[Pasted image 20250605094218.png]]

4.  **Real-World Considerations:**
    1. In a real robotic arm, what external factors or disturbances might affect the joint's position, and how would a PID controller help mitigate these? (Think about things not explicitly modeled in our simplified simulation).
	
		| External Factor | How it affects the system | How PID helps  |
		|-----------------------------|--------------------------------------------------------------------|-------------------------------------------------------------------------------------|
		| **Friction** (static & dynamic) | Causes resistance to motion; may prevent small movements.           | PID, especially the **I-term**, accumulates error to overcome static friction.     |
		| **Backlash** (mechanical play)  | Causes dead zones or delayed response when direction changes.       | PID reduces impact by continuous correction, but additional compensation may help. |
		| **Load variation** (e.g., lifting objects) | Requires more torque for heavier loads.                             | PID dynamically adjusts output to maintain setpoint.                               |
		| **External forces** (e.g., touch, collisions) | Pushes joint off position.                                          | PID reacts to disturbances to bring joint back to target.                          |
		| **Sensor noise or drift**     | Leads to inaccurate feedback.                                     | Filtering is often needed; **D-term** reduces effects of sudden fluctuations.      |
		| **Thermal expansion**         | Causes structural changes affecting accuracy.                      | **I-term** slowly compensates over time.                                            |
		| **Power supply fluctuation**  | Affects motor performance.                                         | PID tries to maintain performance, but hardware-level solutions may be needed.     |

    2. What are some limitations of the simplified robotic arm joint model used in this simulation, and how might a more realistic model be implemented for control system design?

		| Limitation                            | Why it's unrealistic                                                   | Improvements for realism                                                        |
		|---------------------------------------|------------------------------------------------------------------------|---------------------------------------------------------------------------------|
		| **No velocity or acceleration modeling** | Real systems have inertia and velocity dependence.                      | Introduce separate velocity and acceleration states using Newtonian dynamics.  |
		| **No nonlinear effects** (friction, backlash) | Real mechanisms behave nonlinearly in many regions.                    | Add friction models, backlash handling, nonlinear torque profiles.             |
		| **Instantaneous control response**      | Real actuators have latency and limited rates.                         | Include actuator dynamics and saturation limits.                               |
		| **No sensor noise**                     | Real sensors introduce random errors.                                  | Add noise simulation and filters (e.g., moving average, Kalman filter).        |
		| **No external disturbances**            | Real environment isn't perfectly isolated.                             | Simulate random forces or user-defined disturbances.                          |
		| **No feedback delay**                   | Real systems have sensor or control delays.                            | Introduce communication and processing delays.                                 |
		| **No joint limits or saturation**       | Physical joints have motion constraints.                               | Implement joint angle limits and signal clamping.                              |

5.  **Further Improvements:**
     Suggest one or two ways you could potentially improve the control performance beyond basic PID tuning for this robotic arm joint (e.g., advanced control techniques, modifications to the system).

     - **Model Predictive Control (MPC):** Uses a dynamic model to predict future behavior and optimize control input over a time horizon.  
     - **Feedforward Control:** Anticipates the required control input based on known system dynamics or disturbances.  
     - **Kalman Filtering:** Reduces sensor noise and improves state estimation, especially when combined with PID.  
