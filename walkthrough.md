# MultiversX Accelerator DAO: The Redesign
**Final Architecture & Execution Strategy**

## 1. Executive Summary
We have transformed the Accelerator DAO from a passive grant giver into a **Strategic Revenue Engine**.
*   **Old Model**: Subsidies for existence.
*   **New Model**: Capital injection for **Productivity** (Revenue/TVL).
*   **Goal**: Ignite a self-sustaining DeFi economy ($1.5M/mo Revenue Potential) via "Canonical" primitives and "Active Yield" boosts.

---

## 2. The Architecture (Artifacts)

### A. The Constitution (`acceleratorDAO.md`)
*   **The "Canonical" Mandate**: We fund only *one* King per vertical (Lending, Perps) to concentrate liquidity.
*   **Milestone Grants**: Capital is released in tranches (Seed -> Traction -> Revenue) based on execution, not promises.
*   **Treasury Conservation**: Unused emissions are rolled over. We do not burn money on mediocrity.

### B. The Engine (`liquidity_boost_framework.md`)
*   **Productivity Score**: We reward **Fees Generated**, not just TVL.
    $$ Score = (Fees^2) / TVL $$
*   **lsEGLD Cap**: To boost liquidity, you must hold `lsEGLD`. This creates a permanent demand sink for the base asset.

### C. The Product Catalog (`activeyieldstrategies.md`)
*   **User Menu**: 5 Simple "Vaults" (Anchor, Magnet, Accumulator, etc.) that abstract complexity.
*   **Builder Reference**: 15 standardized strategies (e.g., Basis Trade, Loop Staking) for devs to build.

---

## 3. The Execution Plan (`genesis.md`)
**"Operation Revenue" (Months 1-6)**
*   **Budget**: 100k EGLD / Month.
*   **The 4-Pool Strategy**:
    1.  **The Magnet (35%)**: Deep `lsEGLD/USDC` liquidity ($20M target).
    2.  **The Accumulator (25%)**: Leveraged Staking Vault (Using LP Collateral).
    3.  **The House (25%)**: Cross-Margin Perps Liquidity.
    4.  **The Anchor (15%)**: Peg Stability (`EGLD/lsEGLD`).
*   **Financial Goal**:
    *   **Phase 1**: Kickstart to $2M daily volume (10x growth).
    *   **Phase 3**: Scale to $70M daily volume (100x growth) -> $1.5M Monthly Revenue.

---

## 4. Technical Implementation (`strategy_standard_spec.md`)
*   **Active Yield Strategy Standard (AY-SS)**: A Rust trait for standardized Vaults.
*   **Dynamic SFTs**: Positions are tokenized as Dynamic NFTs/SFTs for composability.
*   **Registry**: On-Chain Whitelist for "Code is Law" governance.
*   **Key Security**: Rewards are **Claimable** (Option A), not auto-compounded, keeping accounting clean.

## 5. Risk & Security (`risk_assessment_lp_collateral.md`)
*   **Critical Finding**: Using LP Tokens as Lending Collateral is high-risk ("Flash-Crash" Oracle Attacks).
*   **Mandatory Mitigations**:
    1.  **TWAP Oracles** (Min 30 min). No Spot Price.
    2.  **Isolation Mode**: No cross-margin with volatile assets.
    3.  **LTV Cap**: STRICT 60% limit to buffer IL spirals.

---

## 6. Next Steps (Immediate)
1.  **Deploy Registry**: Launch the `AcceleratorRegistry` smart contract.
2.  **Genesis Grant**: Open RFP for the "Canonical Perps" and "Canonical Lending" teams to integrate the AY-SS Standard.
3.  **Seed Liquidity**: Move the first tranche of 100k EGLD to the "Magnet" and "Anchor" pools.
