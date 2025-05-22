## Reactive Navigation
- `A goal-oriented machine that can sense and act without building a global map.`
- Reacts to stimuli from the environment in real-time, often without memory.

### Braitenberg Vehicles
- Simple goal-seeking robots characterized by a direct connection between sensors and motors.
- __Sensor__ --> __Actuator__
- Behavior emerges from the wiring of connections (e.g., light sensors to wheels for phototaxis).

### Simple Automata (Bug Algorithms)
- Reactive robots (often called "bugs") that seek goals while avoiding obstacles.
- Use a finite state machine to switch between behaviors (e.g., go-to-goal, wall-follow).
- __Sensor__ --> Automata (FSM) --> __Motor__

---

## Map-Based Planning
- `A goal-oriented machine that can sense, plan, and act using a map of its environment.`
- Planning is done before movement based on known or assumed map data.

### D* (Dynamic A*)
- A dynamic version of A* used for efficient replanning when the environment changes.
- Suitable for unknown or partially known environments.

### Distance Transform
- Converts a map with the goal marked to a **gradient field** representing distances to that goal.
- Obstacles = 0, Free space = increasing values as distance increases.
- **Does not give a path directly**, but allows following the **steepest descent** to reach the goal.
- Efficient for **static goals**, but costly to recompute if the goal moves.

---

## Road-Mapping
- Planning = construct a roadmap; Query = use it to find paths.
- Distance Transform and D* do heavy computation in planning but offer fast queries.
- If the goal changes, the planning must often be redone (except in some dynamic planners).
- A roadmap, once built, allows any-to-any pathfinding (like a train network).

---

### Probabilistic Roadmap Method (PRM)
- Suitable for **multi-query** problems in static environments.
- Builds a graph by:
  - Sampling N random points in free space.
  - Connecting each point to nearby neighbors using valid (obstacle-free) edges.
- Lower computational cost compared to full-space planners.
- **Offline planning**, but highly efficient queries after setup.

---

### Lattice Planner
- Map is structured with feasible, pre-defined motion patterns (e.g., grid of drivable paths).
- Useful for systems with **non-holonomic constraints** (e.g., cars that can’t move sideways).
- Motion primitives define the allowed transitions between states.

---

### Rapidly Exploring Random Tree (RRT)
- A **sampling-based algorithm** for **single-query** planning in high-dimensional or complex spaces.
- Builds a tree by:
  - Sampling a random point.
  - Extending from the closest existing node toward it.
  - Connecting if the path is valid (collision-free).
- RRT* (an improved version) adds **path refinement and asymptotic optimality**.

---

### 📍 Key Differences: RRT vs PRM

| Feature              | **RRT (Rapidly-exploring Random Tree)** | **PRM (Probabilistic Roadmap)**         |
|----------------------|------------------------------------------|------------------------------------------|
| **Build Style**      | Incremental tree from start              | Graph of sampled points                  |
| **When Built**       | During query time (online)               | Before query (offline)                   |
| **Use Case**         | Single-query (real-time navigation)      | Multi-query (reusable maps)              |
| **Structure**        | Tree (directed, rooted at start)         | Graph (undirected, multiple components)  |
| **Goal Biasing**     | Often biases sampling toward the goal    | Not typical in standard PRM              |
| **Path Refinement**  | Optional (e.g., RRT*)                    | Yes (e.g., shortest path algorithms)     |

