# Reward Types in RugPull

OVR refers to rewards that are fully validated through on-chain staking contracts. When a user stakes tokens using a fixed-term option, all reward calculations follow contract-defined rules such as APR, duration, and lockup conditions. Since the contract handles reward generation and updates directly, the system ensures full transparency and guarantees that no reward data can be altered by the backend.

This model allows RugPull to maintain a verifiable reward history for each position. Because every update and distribution is anchored to an on-chain event, users gain clear insight into how their staking positions accumulate yield over time. OVR helps ensure fairness across the entire platform and removes opportunities for manipulation or inconsistencies. It is ideal for users who prefer maximum transparency and blockchain-backed validation.

***

### **Off-chain Calculated Rewards (OCR)**

_Backend-assisted reward calculation for flexible or promotional yield_

OCR refers to yield that is computed off-chain by RugPull’s backend systems. This model is used for mechanisms such as promotional boosts, referral commissions, and certain airdrop-based reward campaigns. The backend tracks user actions, eligible events, and bonus rules, then calculates reward amounts accordingly. While these rewards are stored off-chain initially, users must still claim them through a signed transaction, keeping the system non-custodial and secure.

OCR gives the platform flexibility to introduce new earning programs without deploying new smart contracts every time. However, because the validator (backend) cannot rely on a fully on-chain deterministic model, users receive fewer guarantees of consistency compared to OVR. Variations may occur based on campaign timelines, referral rules, or platform-wide reward adjustments. OCR rewards are best suited for growth-oriented features rather than core staking yield.

***

### **When to Use Each Reward Type**

* **OVR** is used for fixed-term staking, predictable APR, and yield that must be fully auditable.
* **OCR** supports referrals, bonuses, limited-time campaigns, and airdrops where flexibility is required.

Both models complement each other:\
OVR delivers predictable, transparent staking rewards, while OCR enables RugPull to grow its ecosystem without compromising user asset control.
