# RugPull Reputation Scoring

### **1. Completeness**

This measures whether the submitted data or activity is full, accurate, and not missing important parts.\
A node with high Completeness provides full records without gaps, helping the network verify that all required actions were executed properly.

***

### **2. Consistency**

Consistency checks whether the data or activity remains uniform across different sessions or time periods.\
Nodes that behave reliably and produce predictable outputs earn higher Consistency scores.

***

### **3. Timeliness**

Timeliness reflects how quickly a node responds or submits required data.\
Faster response times indicate better performance and more value to the network, especially during high-load operations.

***

### **4. Availability**

Availability measures how often the node is online and operating correctly.\
Nodes with strong uptime provide stability to the RugPull ecosystem and earn a higher Availability score.

***

### **Weighted Reputation Formula**

To evaluate each participant fairly, RugPull assigns a weighted score based on the four characteristics above.

**Reputation Score (R):**

$$
R = w_A \cdot A + w_C \cdot C + w_T \cdot T + w_F \cdot F
$$

Where:

* **A** – Availability
* **C** – Completeness
* **T** – Timeliness
* **F** – Consistency (Reliability)
* **wA, wC, wT, wF** – Weighting factors for each metric

**Weight Condition:**

$$
w_A + w_C + w_T + w_F = 1
$$

These weights allow RugPull to adjust the importance of each factor depending on network goals — for example, prioritizing uptime over speed, or consistency over completeness.
