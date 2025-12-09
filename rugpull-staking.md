# RugPull Staking

### **1. How Staking Works**

RugPull uses a fixed-term staking model where users lock tokens for a selected duration (30–365 days). Rewards begin accumulating immediately after the stake is confirmed on-chain.

Key characteristics:

* Rewards accumulate every second.
* Stakes are secured through smart contracts.
* Users maintain full ownership of their wallet and assets.
* All positions are visible in the dashboard in real time.

***

### **2. Delegated Staking (Routers)**

In future versions of RugPull, users may also be able to delegate their stake to routers (or network nodes), creating a **shared-risk, shared-reward** model.

#### **2.1 Why Delegation Matters**

Delegation aligns financial incentives between:

* Token holders (delegators)
* Network routers (operators)

Routers with more delegated stake may handle more traffic, generating greater rewards for both themselves and their delegators.

***

### **3. Rewards**

Rewards are calculated continuously and distributed every second based on:

* Chosen staking term
* Token amount
* APR associated with the term
* Router performance (in delegated mode)

Your dashboard displays:

* Active stakes
* Claimable rewards
* Total earnings
* History of claims and unstake actions

***

### **4. Unstaking**

RugPull provides two unstaking options depending on the staking model:

#### **4.1 Fixed-Term Unstaking**

For fixed terms (30–365 days):

* Full rewards are unlocked at maturity
* Early unstake may result in reduced rewards or fees (depending on term rules)

#### **4.2 Delegated Unstaking (Future Feature)**

If using router delegation in the future:

* Unstaking requires a **7-day unlock period**
* Tokens remain locked but no longer earn rewards during this time
* After 7 days, tokens become withdrawable

***

### **5. Commission Fees (Router Mode)**

Routers may charge commission fees on rewards generated through delegated stakes.\
This helps cover operational infrastructure costs such as hosting, bandwidth, and uptime management.

Routers may compete for delegators by offering:

* Lower commission fees
* Higher uptime and reliability
* Better performance scores

***

### **6. Slashing (Future Risk)**

RugPull may introduce a slashing mechanism in later decentralized versions.

#### **6.1 What is Slashing?**

Slashing is the destruction of a portion of a router’s or delegator’s staked tokens if malicious activity is detected — for example:

* Falsifying data
* Misreporting performance
* Censoring or blocking network transactions

#### **6.2 Current Status**

There is **no slashing mechanism active today**.\
Future updates may add automated, on-chain slashing once the network becomes fully decentralized.
