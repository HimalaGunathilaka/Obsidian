## 📐 Denavit-Hartenberg Parameters Table

| Parameter   | Physical Meaning                                                           | Symbol        | Type (Constant / Variable)           |
| ----------- | -------------------------------------------------------------------------- | ------------- | ------------------------------------ |
| Joint angle | Angle between x<sub>j</sub> and x<sub>j−1</sub> about z<sub>j−1</sub>      | θ<sub>j</sub> | Revolute joint variable or constant  |
| Link offset | Distance from origin of frame {j} to x<sub>j−1</sub> along z<sub>j−1</sub> | d<sub>j</sub> | Constant or prismatic joint variable |
| Link length | Distance between z<sub>j</sub> and z<sub>j−1</sub> along x<sub>j−1</sub>   | a<sub>j</sub> | Constant                             |
| Link twist  | Angle from z<sub>j</sub> to z<sub>j−1</sub> about x<sub>j−1</sub>          | α<sub>j</sub> | Constant                             |
| Joint type  | R = Revolute, P = Prismatic (R=0, P=1 by convention)                       | τ<sub>j</sub> | Constant                             |
