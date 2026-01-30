# Genesis Execution Roadmap: Start -> Monthly Recurring

This roadmap outlines the operational sequence for the Accelerator DAO to deploy 100,000 EGLD/month across the 4 core strategies, including the development requirements for the Perpetual DEX.

---

## I. Strategy Execution Matrix

| Strategy | **Easy Version** (Immediate) | **Optimal Version** (Needs Dev) | DAO LP (Start) | User Boosting (Monthly) |
| :--- | :--- | :--- | :--- | :--- |
| **1. The Magnet** | xExchange V2 (Standard LP pool) | xExchange V3 (Concentrated/CLMM) | 35,000 EGLD | Active (Cap @ 15%) |
| **2. The Accumulator** | Standard Lending (lsEGLD supply) | Custom "Looping Vault" Contract | 25,000 EGLD | Active (Cap @ 15%) |
| **3. The House** | N/A (Requires Day 1 Dev) | **Hyperliquid-Style Vault** | 25,000 EGLD | Active (Cap @ 15%) |
| **4. The Anchor** | StableSwap (Fixed rate) | StableSwap (Sync with LS Rate) | 10,000 EGLD | Active (Cap @ 15%) |
| **5. The Bond** | *(Optional)* | *(Optional)* | -- | -- |

---

## II. Step-by-Step Execution Plan

### Phase 1: T-Minus 0 (The Start)
**Goal: Establish the Protocol-Owned Liquidity (POL) Floor.**

1.  **Fund The Anchor (Day 1)**: Deploy **10,000 EGLD** into the `EGLD/lsEGLD` StableSwap pool. This ensures that users can later swap for `lsEGLD` to participate in other strategies with zero slippage.
2.  **Initialize The Magnet (Day 1)**: Deploy **35,000 EGLD** (converted to `lsEGLD`) into the `lsEGLD/USDC` xExchange V2 pool. 
    *   *Note*: If the DAO lacks USDC, partner with a stablecoin provider or borrow USDC against EGLD via Lending.
3.  **Bootstrap The Accumulator (Day 2)**: Supply **25,000 EGLD** (as `lsEGLD`) into a Lending Protocol. This creates the "borrow supply" necessary for users to perform leveraged loops.
4.  **Codify The House (Ongoing)**: Initiate the development of the Perpetual DEX / USDX Vault.
    *   **Milestone 1**: Smart contract for the "House LP" (HLP style).
    *   **Milestone 2**: Oracle integration (real-time mark price).
    *   **Milestone 3**: Fee switch and PnL settlement.

### Phase 2: Month 1 (The Incentive Activation)
**Goal: Attract external capital and drive the Staking Flywheel.**

1.  **Activate Boosting (Day 7)**: Open the **AcceleratorRegistry**. Users who stake their LP tokens (Magnet/Anchor) or supply to the Accumulator receive a portion of the unallocated budget to reach the **15% APR Target**.
2.  **Enforce the lsEGLD Cap**: The rewards contract must verify that the user's boosted liquidity is matched 1:1 with `lsEGLD`.
3.  **Weekly Monitoring**: Calculate the **Productivity Score** ($S_{prod} = Fees^2 / TVL$). If a pool is inefficient (low volume), prepare to pivot incentives.

### Phase 3: Monthly Recurring (The Reinvestment)
**Goal: Compound GAINS back into the ecosystem.**

1.  **Reinvestment Fund Audit**: On the 1st of every month, calculate the Fund's growth (20% Net Fee Share + 100% DAO LP Yield). 
2.  **POL Deepening**: 100% of the Reinvestment Fund is converted back to LP positions (EGLD + USDC/lsEGLD) and added to the existing pools.
3.  **Market Maintenance**: Check the `EGLD/lsEGLD` peg in **The Anchor**. If the peg deviates, redirect part of the reinvestment fund to re-balance.
4.  **Pivot Decisions**: If the **Perpetual DEX (The House)** is generating the highest fees per dollar (highest $S_{prod}$), move 10% of the Magnet/Anchor incentive budget directly into the Perps "House Vault" rewards.

---

## III. Detailed Strategy Instructions

### 1. The Magnet (`lsEGLD / USDC`)
*   **Easy**: Simply provide liquidity to the existing xExchange V2 pool. 
*   **Optimal**: Develop a custom V3 interface that uses Concentrated Liquidity. This allows the DAO to put its 35k EGLD in a tight price range, maximizing fee capture.
*   **DAO Action**: Put 35,000 EGLD into LP. Pay users extra "Boost" EGLD only if their base LP yield is < 15%.

### 2. The Accumulator (Leveraged Staking)
*   **Easy**: Users manually supply `lsEGLD` to Lending and borrow `EGLD`.
*   **Optimal**: A 1-click **Vault Contract** that performs the loop in a single transaction (Flashloans).
*   **DAO Action**: Put 25,000 EGLD as "Supply" in Lending. Boost the interest users earn so their "Net Yield" hits exactly 15%.

### 3. The House (Perpetuals) - **MANDATORY DEV**
*   **Goal**: Create a Hyperliquid-parity counter-party vault.
*   **Tech Needs**: 
    1.  A vault that accepts `lsEGLD`, `USDC`, and `Magnet/Anchor LP tokens`.
    2.  An internal ledger (USDX) to track trader trades versus the House Vault.
*   **DAO Action**: Day 1: Deposit 25,000 EGLD into the "House LP" (USDX) vault. No user incentives needed (Organic yield will be high).

### 4. The Anchor (`EGLD / lsEGLD`)
*   **Easy**: Use the existing StableSwap pool with a manually set fixed rate.
*   **Optimal**: Integrate the StableSwap price oracle with the **LiquidStaking Contract**. The rate must update automatically as staking rewards accumulate.
*   **DAO Action**: Deposit 10,000 EGLD into POL. Boost users who provide liquidity to ensure the peg is hard-fast.

---
*Report generated by /defi-specialist Unit.*
