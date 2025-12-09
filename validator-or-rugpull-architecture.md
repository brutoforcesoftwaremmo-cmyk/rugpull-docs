# Validator | RugPull Architecture

### **Overview**

The RugPull Validator is a core component responsible for verifying staking transactions, validating reward calculations, and ensuring that every interaction with the protocol follows the correct on-chain and off-chain rules.\
While the smart contracts handle custody and yield mechanics, the Validator acts as a logic layer that checks, organizes, and confirms all activity before it is stored, indexed, or rewarded within the RugPull ecosystem.

In the current design, the Validator operates as a single, centralized verifier to guarantee consistent behavior and predictable performance during the early stages of the platform.\
As RugPull evolves, the Validator will transition into a decentralized committee model. Multiple validators will share verification duties, cooperating through a consensus mechanism to increase transparency, reduce trust assumptions, and ensure that no single actor can compromise system integrity.

The Validator ensures the following:

* All staking and withdrawal requests follow the correct parameters
* Users cannot bypass rules such as minimum stake amount, penalties, or term requirements
* Reward calculations match on-chain data
* Fraudulent or malformed transactions are rejected before they reach the accounting layer

***

### **Transaction Verification**

The Validator analyzes each staking-related event to confirm that it meets protocol requirements. It checks both _user-provided parameters_ and _on-chain confirmations_ before finalizing the operation.

#### **Staking Verification**

* Validates the selected staking term (30–365 days)
* Confirms minimum and maximum stake amounts
* Verifies that the user wallet actually signed the on-chain transaction
* Checks that tokens were transferred correctly to the staking contract
* Registers the new position in RugPull’s indexing layer for dashboard display

#### **Reward Validation**

Rewards are not assigned blindly. The Validator re-computes reward accumulation using:

* The term APR
* The position start time
* The lock duration
* Claim history
* Whether the position has matured

This prevents incorrect payouts caused by RPC delays, user manipulation attempts, or out-of-sync client states.

#### **Withdrawal Validation**

For withdrawal or claim requests, the Validator checks:

* Whether the position has matured
* Whether the user is eligible for full or partial rewards
* Whether early withdrawal rules apply
* Fee deductions (if applicable)
* On-chain confirmation of token transfers

Only after all steps pass does the Validator mark a position as closed.

***

### **Data Integrity & Session Handling**

Each user interaction creates a “session” of data that includes:

* Wallet address
* Action type (stake, claim, withdraw)
* Timestamp
* Token amount
* Selected term
* Reward state at the moment of the action

The Validator stores and indexes this session data securely so RugPull can:

* Display real-time dashboards
* Reconstruct reward history
* Audit inconsistencies
* Produce verifiable accounting reports

In future versions, session data will be notarized on-chain to provide cryptographic proof of correctness.

***

### **Security**

In RugPull’s current phase, the Validator operates under its own security assumptions.\
Because it does not derive security from a blockchain consensus directly, the system applies strict safeguards to maintain correctness.

#### **1. Fallback to On-Chain Data**

If the Validator is offline or under maintenance, users can still rely on smart contracts.\
Reward states, balances, and stake positions remain accessible and verifiable since custody is fully on-chain.

#### **2. Anti-Fraud Checks**

The Validator prevents:

* Double claiming
* Manipulated timestamps
* Fake reward events
* Early-withdrawal bypass attempts
* RPC spoofing or invalid transaction injections

#### **3. Future Decentralization**

The Validator will evolve from a single service into a distributed network of economically collateralized validators.\
Each validator will be required to stake RugPull tokens to participate in the verification process, providing:

* Sybil resistance
* Economic penalties for malicious activity (slashing)
* A trust-minimized environment for transaction validation

This ensures that no single party can manipulate staking results or influence reward distribution.
