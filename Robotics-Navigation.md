## Reactive navigation
- `A goal oriented machine that can sense and act.`
- 
### Braitenberg vehicles
- Simple goal achieving robots which are characterized by direct connection between sensors and motors.
__Sensor__ --> __Actuator__
- 
### Simple automata
- Class of reactive robots known as bugs that perform goal seeking in the presense of nondriveable areas or obstacles. 
- The bug has state machine between the sensor and the motors.
__Sensor__ --> Automata --> __Motor__ 
## Map-based planning
- ```A goal oriented machine that can sense, plan and act.```
- A popular algorithm for robot path planning is D* (Dynamic A*).
- __Distance transform__ - Consider a matrix of zeros with just a single element representing the goal. The distance transform of this matrix is another matrix, of the same size but the value of each element is its distance from the original non zero  pixel.
	- Each **free cell** in a grid is assigned a value representing its **distance to the nearest obstacle**. 
	- Obstacles are typically marked with a value of **0**, and free cells get increasing values depending on how far they are from obstacles.
	- **The Distance Transform itself doesn't give a path directly from A to B.**  
		Instead, it **reshapes the map** into a gradient field (like a heatmap), and you then **extract the path** by **following the gradient** — usually moving from the start (A) **toward the goal (B)** using the steepest descent or ascent, depending on how the DT is computed.
### Road-mapping
- The analysis of map is the __planning phase__ of robotic path planning.
- The __query phase__ uses the result of the planning phase to find a path from A to B.
- Distance transform and D∗, require a signiﬁcantamount of computation for the planning phase, but the query phase is very cheap.However the plan depends on the goal. If the goal changes the expensive planning phase must be re-executed. Even though D∗ allows the path to be recomputed as the costmap changes it does not support a changing goal.
- The roadmap need only be computed once and can then be used like the train network to get us from any start location to any goal location.
### Probabilistic Roadmap Method (PRM)
- The high computational cost of the distance transform and skeletonization methods makes them infeasible for large maps and has led to the development of probabilistic methods. These methods sparsely sample the world map.
- The planning phase ﬁnds N random points, that lie in free space. Each point is connected to its nearest neighbors by a straight line path that does not cross any obstacles, so as to create a network, or graph, with a minimal number of disjoint components and no cycles.
### Lattice Planner
- 
### Rapidly Exploring Random Tree (RRT)
