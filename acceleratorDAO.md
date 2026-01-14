# The MultiversX Accelerator DAO
**Constitution & Strategic Mandate**

## I. The Mission: A Revenue Engine
The Accelerator DAO is not a charity. It is the **Strategic Venture Arm** of the MultiversX network. Its mandate is to allocate capital to projects that do one thing: **Generate On-Chain Financial Value**.

We continuously transition from an inflationary subsidy model to a **Deflationary Revenue Engine**. Every allocated EGLD must return >1.0 EGLD in long-term network value (Fees, Burns, Liquidity Depth, Velocity).

## II. The "Canonical" Strategy
To compete with integrated "Super-App" chains, we do not fragment our limited emissions. We fund **One Canonical Primitive** per vertical to guarantee deep liquidity and composability.

### The "King of the Hill" Mandate
*   **One King**: Only one project per vertical (e.g., *The* Perps DEX, *The* Lending Protocol) receives "Canonical Status" and the massive associated Grants & Boosts.
*   **Performance Lease**: Canonical Status is leased. If the King becomes "lazy" (fails to innovate, low uptime), the DAO initiates a **"Challenger Grant"** to fund a direct competitor.
*   **Open Source**: Canonical projects must open-source their smart contracts to prevent vendor lock-in.

## III. The Grant Framework: Milestone-Based Investments
We invest based on **Clear Roadmaps** and **Deliverables**.

### 0. Purpose of Funding
Funds are strictly allocated for **Product Development**, **DevOps/Infrastructure**, and **Initial Liquidity Seeding** (recirculated within the ecosystem). Grants are **not** to be used for external marketing agencies or speculative buybacks.

### 4. Treasury Conservation
The DAO is **not obligated** to spend its entire monthly budget. 
*   **Rollover**: If no project or pool meets the high "Productivity Score" threshold, the emissions for that epoch are **retained in the Treasury** (or burned, pending governance vote).
*   **Quality over Quantity**: We prioritize preserving capital over funding mediocre activity.
Projects apply for a discrete **Funding Package** (e.g., "Seed Round: $1M"). This package is broken down into specific operational milestones.
*   **Structure**: Grants are not open-ended streams. They are fixed commitments.
*   **Renewal**: Once a grant package is fully vested and milestones are met, the Project must apply for a new round (e.g., "Series A") if they require further capital. This ensures re-evaluation of performance.

### 2. Milestone Tranching ("Perform or Freeze")
Funds are released only upon verification of Milestones.
*   **Tranche 1 (Deployment)**: Released upon mainnet launch/audit.
*   **Tranche 2 (Traction)**: Released upon hitting specific KPIs (User count, Volume targets).
*   **Tranche 3 (Revenue)**: Released upon activating the Fee Switch.
*   *Mechanism*: If a milestone is missed, the subsequent tranche is **Frozen** until remediation.

### 3. Value to Network
The "Return on Investment" for the DAO is the **On-Chain Velocity**, the **Gas Fees**, and the **Demand for EGLD** created by the app's usage.

## IV. The Liquidity Boost ("Active Yield")
Distinct from building grants, the DAO allocates 20% of emissions to **Dynamic Liquidity Incentives**.
*   **Purpose**: To subsidize the cost of capital for high-value pools (Lending, Perps).
*   **Mechanism**: Boosts are calculated algorithmically based on the **Productivity Score** (Revenue/TVL).
*   **Dynamic Nature**: This is not a fixed grant. It is a fluctuating APY top-up that moves automatically to where the financial activity is highest. See [Liquidity Boost Framework](./liquidity_boost_framework.md).

## V. DAO-Owned Liquidity (DOL) & Market Making
Grants are not always "Spent". A crucial portion of the treasury is allocated to **Liquidity Seeding**.

### 1. DAO-Owned Liquidity (DOL)
Instead of giving tokens to a project to incentivize liquidity, the DAO **"Leases" Liquidity**.
*   **Mechanism**: The DAO provides EGLD into the project's pools (e.g., EGLD/USDC) but **retains ownership** of the LP tokens.
*   **Benefit**: The DAO earns trading fees and sustains permanent depth.

### 2. Market Making Mandate
Canonical projects must maintain healthy order books.
*   **Grant Usage**: Projects are authorized to use a portion of their initial grant tranche to seed MM bots.
*   **KPI**: "Spread Tightness" and "Order Book Depth" are valid KPIs for the release of subsequent tranches.

## VI. Governance: "Structure A"
We balance **Builder Agility** with **DAO Security**.

1.  **Builder Keys**: Builders hold Admin keys. They can ship instantly.
2.  **The Time-Lock**: Critical changes (e.g., fee switching) must have a **Time-Lock** (e.g., 48h).
3.  **DAO Veto**: The DAO Council holds a "Security Veto" key to **Pause** contracts if malicious intent is detected.
4.  **Breach of Contract**: If a Canonical Project acts maliciously, the DAO votes to **Revoke Status** and redirect support to a Challenger.

## VII. Implementation
*   **Grants**: On-chain Proposal -> Milestone Verification -> Release.
*   **Boosts**: Weekly Merkle-drops based on the Liquidity Boost Framework.
