# RugPull Reputation Scoring

### **1. Reputation Metrics**

Each transaction contributes data used to measure four fundamental characteristics:

#### **1.1 Completeness (C)**

Evaluates whether the response or data packet includes all required elements. Missing or incomplete outputs reduce the score.

#### **1.2 Consistency (N)**

Measures how uniform the node’s performance is across multiple sessions. Nodes that behave predictably earn higher consistency scores.

#### **1.3 Timeliness (T)**

Reflects the node’s response speed and ability to deliver data within expected time windows.

#### **1.4 Availability (A)**

Represents how often the node is online, reachable, and capable of serving requests.

***

### **2. Notation**

* **R** — Final reputation score
* **C** — Completeness
* **N** — Consistency
* **T** — Timeliness
* **A** — Availability

Weights (relative importance of each metric):

$$
R = w_C \cdot C \;+\; w_N \cdot N \;+\; w_T \cdot T \;+\; w_A \cdot A
$$

***

### **3. Reputation Formula**

The final reputation score is computed as a weighted sum of the four metrics:

***

$$
R = w_C \cdot C + w_N \cdot N + w_T \cdot T + w_A \cdot A
$$

### **4. Dynamic Weight Allocation**

To ensure the scoring model adapts to real-world node behavior:

#### **4.1 Fixed Weight for Completeness**

Completeness receives a **fixed weight of 0.5**, acknowledging its importance:

$$
w_C = 0.5
$$

Completeness is prioritized because missing or invalid data poses the highest operational risk.

#### **4.2 Remaining Weights (N, T, A)**

The remaining 0.5 weight is distributed proportionally across Consistency, Timeliness, and Availability based on how much each metric **varies** among nodes.

Metrics with greater variability are given **more weight**, meaning the system rewards nodes that outperform peers where the network struggles most.

Let:

* **N₍t₁,t₂₎** — all observed Consistency values in time period \[t1,t2]\[t\_1, t\_2]\[t1​,t2​]
* **T₍t₁,t₂₎** — all observed Timeliness values
* **A₍t₁,t₂₎** — all observed Availability values

Standard deviations:

* **σ(N₍t₁,t₂₎)**
* **σ(T₍t₁,t₂₎)**
* **σ(A₍t₁,t₂₎)**

#### **Weight formulas:**



$$
w_T = 0.5 \cdot \frac{\sigma(T)}{\sigma(N) + \sigma(T) + \sigma(A)}
$$

$$
w_A = 0.5 \cdot \frac{\sigma(A)}{\sigma(N) + \sigma(T) + \sigma(A)}
$$

$$
w_C + w_N + w_T + w_A = 1
$$

***

### **5. Interpretation**

* Metrics with **higher variability** receive a **greater portion** of the dynamic weight.
* This makes the reputation score more sensitive in areas where nodes differ the most.
* During periods where uptime is stable but response speed varies, Timeliness receives more weight, guiding the reward system toward performance improvements.

***

### **6. Definitions Recap**

| Metric                     | Description                              |
| -------------------------- | ---------------------------------------- |
| **R**                      | Final reputation score                   |
| **C**                      | Completeness — all required data present |
| **N**                      | Consistency — stability over time        |
| **T**                      | Timeliness — response speed & recency    |
| **A**                      | Availability — uptime and accessibility  |
| **w\_C, w\_N, w\_T, w\_A** | Metric weights (sum to 1)                |
