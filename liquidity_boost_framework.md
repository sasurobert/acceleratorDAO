# The Liquidity Boost Framework
**The Algorithmic Engine for Active Yield**

## 1. Core Philosophy: Value, Not Idleness
This framework governs the distribution of the **20% "Active Yield" Emissions**. Its purpose is to incentivize **Productivity**, not just Total Value Locked (TVL). We do not pay for idle capital; we pay for capital that works, generates fees, and creates depth for the "Canonical" primitives.

## 2. The "lsEGLD Cap" Mechanism
To prevent mercenary capital from farming rewards without supporting the ecosystem's base money, all boosts are gated by **Liquid Staked EGLD (lsEGLD)**.

*   **The Rule**: A user's "Boostable Liquidity" is capped at **100% of the value of lsEGLD** they hold (or use in the position).
*   **Formula**:
    $$ \text{Boostable\_Liquidity} = \min(\text{Total\_Liquidity}, \text{lsEGLD\_Value} \times 1.0) $$
*   **Example**:
    *   User pairs $1,000 USDC with $100 lsEGLD in a CLMM.
    *   Total Liquidity: $1,100.
    *   lsEGLD Value: $100.
    *   **Boostable Amount**: $100. (The remaining $1,000 earns base yield but 0% Boost).
    *   *Incentive*: To boost the full $1,100, the user implies they should have come with ~$550 lsEGLD + $550 USDC.

This enforces a permanent demand sink: **To import $1M of outside capital (USDC), you must buy/hold $1M of lsEGLD.**

## 3. The "Productivity Score" (The Algorithm)
We do not reward TVL. We reward **Efficiency**. A small pool generating massive volume and fees is more valuable than a massive pool generating dust.

*   **The Metric**: Capital Efficiency Score ($S_{prod}$).
*   **Formula**:
    $$ S_{prod} = \frac{(\text{Total\_Fees\_Generated})^2}{\text{TVL}} $$
*   **Definition of Fees**: "Total Fees Generated" refers to the gross financial value captured by the protocol from user activity.
    *   *Note*: This metric is used purely for scoring. The **Builder keeps 100%** of these fees. The DAO uses this data only to calculate the "Economic Density" of the pool.
*   **Why Squared?**: Squaring the fees significantly rewards high-revenue activity.
    *   *Scenario A (Lazy Whale)*: $100M TVL, $100k Fees.
        *   $S = (100k^2) / 100M = 100$.
    *   *Scenario B (Active Yield)*: $10M TVL, $100k Fees.
        *   $S = (100k^2) / 10M = 1,000$.
    *   *Result*: Scenario B receives **10x** the boost allocation per dollar.

## 4. Multipliers & Tiers
The Productivity Score is adjusted by the **Strategic Tier** of the asset/protocol.

| Tier | Description | Multiplier ($M$) |
| :--- | :--- | :--- |
| **Tier S** | **Canonical Primitives** (The "King" Perps, Lending, lsEGLD pairs) | **2.0x** |
| **Tier A** | **Imported Capital** (USDC, wBTC paired with lsEGLD) | **1.5x** |
| **Tier B** | **Internal Ecology** (EGLD pairs, other ecosystem tokens) | **1.0x** |
| **Tier B-** | **Prediction Markets** (High Velocity, Low TVL) | **1.0x** |
| **Tier C** | **Speculative** (Memes, unverified assets) | **0.0x - 0.5x** |

**Final Score Calculation**:
$$ \text{Allocation\_Weight} = S_{prod} \times M $$

## 5. The "Grace Period" (Kickstart)
New "Canonical" pools cannot generate fees immediately due to lack of liquidity.
*   **Mechanism**: A **10-Day Boost Window**.
*   **Eligibility**: Only for Protocols explicitly whitelisted by Dao Vote as "New Candidate".
*   **Effect**: For 10 days, the Productivity Score is overridden.
    $$ S_{start} = \text{Target\_TVL} \times \text{Median\_Network\_Efficiency} $$
*   *Anti-Gaming*: This allows a cold start. If the project fails to generate real fees by Day 11, the score collapses to the standard formula, and rewards vanish.

## 6. Distribution Cycle
*   **Frequency**: Weekly (Epochs).
*   **Oracles**: Fee data must be verified on-chain (via protocol fee collector contracts) or via Chainlink Functions/Dune API (consensus verified).
