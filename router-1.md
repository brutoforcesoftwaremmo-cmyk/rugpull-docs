# Router

### **1. Overview**

RugPull routers act as geographically distributed relay hubs. Their responsibilities include:

* Managing all incoming and outgoing requests between nodes and validators
* Routing encrypted traffic through secure channels
* Measuring and reporting performance metrics
* Maintaining stable uptime and connectivity
* Earning rewards based on delegated stake and validated network activity

After full decentralization, routers will receive rewards proportional to the **validated bandwidth** they handle across their relays.

***

### **2. Verification Responsibilities**

Routers continuously monitor and report network performance to validators.\
They must submit accurate measurements for:

* **Request size (bytes)** for both incoming and outgoing traffic
* **Latency from node → router**
* **Latency from router → validator**
* **Current status and connectivity health of each attached node**

These metrics allow RugPull to verify traffic quality, detect bottlenecks, score node performance, and allocate rewards fairly.

***

### **3. Rewards Structure**

#### **3.1 Delegate Rewards**

Users can delegate stake to routers.\
Delegators earn rewards proportional to the amount they stake relative to the total router pool.

The total rewards earned by a delegator:

$$
R_d = R_p + \frac{S_d}{T} \cdot (D \cdot I)
$$

Where:

* **R\_d** — Delegate’s accumulated rewards
* **R\_p** — Rewards previously accumulated before the new interval
* **S\_d** — Delegate’s staked amount
* **D** — Tokens distributed per reward interval
* **I** — Number of intervals since last distribution
* **T** — Total tokens staked to the router

***

#### **3.2 Claiming Rewards**

Delegator claim:

$$
R_c = (1 - C) \cdot R_d
$$

Router operator claim:

$$
R_o = C \cdot R_d
$$

Where:

* **R\_c** — Rewards claimed by delegator
* **R\_o** — Rewards claimed by router operator
* **C** — Router’s commission rate

Routers set their own commission, creating competition based on:

* Lower fees
* Higher uptime
* Better performance

***

### **4. Post-Decentralization Reward Model**

When decentralization is activated, routers will no longer earn based only on stake — they will be evaluated by **performance**, especially validated bandwidth and latency.

Router reward:

$$
R = k_B \cdot B \cdot S - K_L \cdot \left( \frac{L_n + L_v}{L_{\max}} \right)
$$

Where:

* **B** — Total validated bandwidth (bytes in + bytes out)
* **L\_n** — Average latency from nodes
* **L\_v** — Latency to the validator
* **S** — Node/network reputation score
* **k\_B** — Bandwidth reward coefficient
* **K\_L** — Latency penalty coefficient
* **L\_max** — Maximum expected latency (normalization)

This model ensures that:

* High-bandwidth routers earn more
* Low-latency routers are rewarded
* Routers handling unreliable or poor-quality connections earn less

***

### **5. Security Requirements**

Routers must uphold strict operational standards:

* Maintain **>75% uptime** (subject to revision)
* Ensure stable connections to a majority of assigned nodes
* Relay traffic without modification
* Submit honest and accurate performance metrics

Routers failing these conditions may, in later versions of the network, be subject to **slashing**, which destroys part of their staked tokens in cases of:

* Malicious reporting
* Tampering with traffic
* Persistent downtime
* Censoring or blocking node traffic

Currently, RugPull does **not** implement slashing, but the architecture is designed to support it once decentralization progresses.
