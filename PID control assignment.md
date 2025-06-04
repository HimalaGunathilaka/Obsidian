1.  **Ziegler-Nichols Method:**
    * What were your determined values for $K_u$ and $T_u$?
		    $K_u$ = 400
		    $T_u$ = 0.1
    * Show your calculations for the initial $K_p, K_i, K_d$ values using the Ziegler-Nichols PID tuning formula.
		    $K_p = 0.6 \cdot K_u = \text{240}$
			$K_i = 2 \cdot K_p / T_u = \text{8000}$
			$K_d = K_p \cdot T_u / 8 = \text{0.0125}$

2.  **Impact of PID Terms:**
    * Describe the effect of increasing $K_p$ (proportional gain) on the system response. How did it affect rise time, overshoot, and steady-state error?
	    - **Rise time** decreases: Controller becomes more aggressive in correcting error, there for the output reaches the set point quickly, 
	    - **Overshoot** increases: Due to the aggressiveness the system might overshoot,
	    - **Steady state error** decreases: Its decreases will be more like $e^{-x}$, not truly getting to the target but gets close.
	    - If we keep increasing $K_p$ at some point there will be oscillation.
	    
    * Describe the effect of increasing $K_i$ (integral gain) on the system response. How did it affect steady-state error and oscillations?
	    * Eliminate **steady state error**, by accumulating error over time and eliminating it.
	    * But due to delayed response, possible to overshoot and cause oscillation.
    * Describe the effect of increasing $K_d$ (derivative gain) on the system response. How did it affect overshoot and settling time?
	    * 

3.  **Performance Comparison:**
    * Compare the system's performance (in terms of settling time, overshoot, and steady-state error) when using the Ziegler-Nichols initial parameters versus your fine-tuned parameters. Explain the differences you observed.
    * Attach the plots for both the Ziegler-Nichols tuned system and your fine-tuned system.

4.  **Real-World Considerations:**
    * In a real robotic arm, what external factors or disturbances might affect the joint's position, and how would a PID controller help mitigate these? (Think about things not explicitly modeled in our simplified simulation).
    * What are some limitations of the simplified robotic arm joint model used in this simulation, and how might a more realistic model be implemented for control system design?

5.  **Further Improvements:**
    * Suggest one or two ways you could potentially improve the control performance beyond basic PID tuning for this robotic arm joint (e.g., advanced control techniques, modifications to the system).