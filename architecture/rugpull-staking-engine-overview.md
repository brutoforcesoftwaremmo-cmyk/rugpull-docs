# RugPull Staking Engine Overview

#### **Overview**

The RugPull staking engine is designed to be lightweight, reliable, and fully non-custodial. Instead of relying on physical network nodes like bandwidth-sharing systems, RugPull’s “nodes” operate through smart contracts and backend services that validate staking actions, track reward cycles, and synchronize user positions.

Users participate by staking supported tokens through their own wallets. All staking interactions occur on-chain, while the backend ensures accurate recordkeeping, reward calculations, and referral or airdrop eligibility.

The staking engine serves two main purposes:

* **Verify and record staking-related events**, including deposits, claims, withdrawals, and the lifecycle of each position.
* **Distribute and update rewards** based on fixed-term APR, platform rules, and user activity.

This hybrid model enables RugPull to provide predictable yield while keeping users in full control of their assets.

***

## **Participating in Staking**

Participating in RugPull is simple and free. No software installation or hardware setup is required.

#### **1. Connect Wallet**

Users begin by connecting a supported wallet such as MetaMask via the dApp.

#### **2. Select Staking Term**

Choose a staking duration (e.g., 30, 60, 90, 180, 365 days) and an amount to stake.\
Each term clearly displays its APR and lockup rules.

#### **3. Confirm Transaction**

The dApp prepares the necessary metadata, and the user signs a transaction directly from their wallet.\
RugPull never accesses or stores private keys.

For more details, see the **How-to Guide**.

***

## **Supported Systems**

RugPull supports all major EVM-compatible wallets and runs on the BNB Chain.\
Users only need:

* A supported browser
* A wallet (e.g., MetaMask)
* Tokens they wish to stake

No specialized device or app installation is required.

***

## **Staking Operation**

Once a user connects and confirms a staking action, the position is automatically registered on-chain. The backend monitors the blockchain to track updates and ensure records stay synchronized.

Each staking action produces:

* A staked amount
* A term duration
* A contract event verifying the stake
* A reward flow that increases over time

All reward updates, claims, and historical data are authenticated through signed transactions and contract events. This ensures that no part of the staking process can be altered or tampered with. The backend only reads and organizes data; it cannot modify user balances or interfere with user-controlled assets.

***

## **Position Health & Status Scoring**

Instead of bandwidth scoring like Grass, RugPull evaluates staking positions using internal status metrics that ensure accurate representation of user earnings and eligibility:

#### **Completeness**

Whether the position contains all the necessary data (amount, APR, term, timestamps, rewards).

#### **Consistency**

Whether the position’s reward calculations remain stable and match on-chain values over time.

#### **Timeliness**

Whether reward updates and claimable amounts are refreshed according to the configured intervals.

#### **Availability**

Whether the staking position can be accessed and read reliably by both the frontend and backend.

These metrics allow RugPull to maintain accurate dashboards and ensure the platform behaves predictably for all users.

***

## **Privacy and Security**

RugPull does not access user wallets, private keys, or personal device data.\
All staking operations happen through cryptographically signed blockchain transactions, and the backend only stores metadata necessary for platform functionality (e.g., referral status, claim history, term configurations).

RugPull interacts exclusively with **public blockchain data**—nothing private from the user’s device is accessed or monitored.
