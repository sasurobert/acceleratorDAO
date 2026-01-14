# Active Yield Strategies: The Menu & Reference Architecture
**From One-Click Vaults to Institutional Financial Products**

This document serves two purposes:
1.  **For Users**: A menu of simplified "Canonical Vaults" for one-click yield.
2.  **For Builders**: A "Reference Architecture" of 15 distinct financial products that can be built on MultiversX to capture the "Canonical" status.

---

## Part I: The User Menu (One-Click Vaults)
The complexity of DeFi must be abstracted. The following 5 vaults represent the detailed implementation of the most critical strategies.

### 1. The Accumulator (Bullish) 🚀
**"I believe in EGLD and want more of it."**
*   **Mechanism**: **Leveraged Liquid Staking Loop**.
*   **Logic**: Deposits `lsEGLD` -> Borrows `Stable` -> Swaps for `EGLD` -> Stakes.
*   **Target**: 3x Staking APY.
*   **Boost Tier**: **S** (Creates Lending Demand).

### 2. The Magnet (Imported Capital) 🧲
**"I have USDC/BTC and want to earn yield on MultiversX."**
*   **Mechanism**: **Boosted Concentrated Liquidity**.
*   **Logic**: Pairs `Imported Asset` + `lsEGLD` in a CLMM.
*   **Target**: Trading Fees + 1.5x Boost.
*   **Boost Tier**: **A** (Necessitates lsEGLD ownership).

### 3. The Market Maker (Delta-Neutral) ⚖️
**"I want high yields but no price risk."**
*   **Mechanism**: **Hedged LP**.
*   **Logic**: `lsEGLD` collateral -> Short Hedge on Perps -> Provide Liquidity.
*   **Target**: Funding Rates + Trading Fees > 20%.
*   **Boost Tier**: **S** (Deepens Perp Liquidity).

### 4. The Oracle (Prediction Markets) 🔮
**"I want to profit from the 'Truth'."**
*   **Mechanism**: **AMM for Outcomes**.
*   **Logic**: LP for top trending prediction markets.
*   **Boost Tier**: **B**.

### 5. The Shield (Lending Base) 🛡️
**"I want safe, passive income."**
*   **Mechanism**: **Over-collateralized Lending**.
*   **Logic**: Base layer for the accumulation loops.
*   **Boost Tier**: **B**.

---

## Part II: The Builder's Catalog (15 Strategic Archetypes)
These are the foundational financial primitives the Accelerator DAO seeks to fund. Builders should use these archetypes to design their "Canonical" applications.

### Core Strategies: Building the Foundation

**1. New Capital Boost ("The Magnet")**
*   **The Hook**: Hold lsEGLD to unlock boosted rewards on other assets you bring to the ecosystem, like $USDC or $wBTC.
*   **Economic Value**: Solves the "Mercenary Capital" problem by forcing imported capital to marry domestic capital (lsEGLD).

**2. CLOB Market Making ("The Specialist")**
*   **The Hook**: Provide liquidity like a pro on a Central Limit Order Book (CLOB) exchange by depositing assets into tight price ranges.
*   **Economic Value**: High-frequency trading creates the "Paper Depth" needed for institutional flows.

**3. Perpetual Futures Vault ("The House")**
*   **The Hook**: Deposit your lsEGLD into a vault that acts as the counterparty (The House) for the Perps DEX.
*   **Economic Value**: The "House" historically always wins. This captures user losses and fees, recycling them into EGLD burns.

**4. Leveraged Staking ("The Accelerator")**
*   **The Hook**: Use your lsEGLD as collateral to borrow stablecoins, swap them for more lsEGLD, and restake it.
*   **Economic Value**: Creates a mechanical, constant "Buy Pressure" on EGLD essentially leveraging the network's own staking rewards.

**5. Real-World Asset (RWA) Backed Yields ("The Bridge")**
*   **The Hook**: Use your lsEGLD holdings as a key to access yields backed by US Treasuries or Private Credit.
*   **Economic Value**: Imports stability. When crypto yields crash, RWA yields sustain the TVL.

### High-Growth & Specialized Strategies

**6. Auto-Compounding Vaults ("The Optimizer")**
*   **The Hook**: "Set and Forget". Smart contracts that auto-harvest and reinvest rewards.
*   **Economic Value**: Maximizes Compound Annual Growth Rate (CAGR) and keeps rewards inside the ecosystem instead of being sold.

**7. Yield Stripping ("The Time Traveler")**
*   **The Hook**: Split your lsEGLD into "Principal" (PT) and "Yield" (YT). Sell the yield today for cash.
*   **Economic Value**: Creates a fixed-income market, essential for corporate treasuries to plan cash flow.

**8. Delta-Neutral Farming ("The Balancer")**
*   **The Hook**: Earn LP fees while creating a perfect hedge against price volatility using Perps.
*   **Economic Value**: Allows risk-averse capital (Pension funds/Treasuries) to provide liquidity, significantly deepening market depth.

**9. Funding Rate Arbitrage ("The Exploiter")**
*   **The Hook**: Profit from the difference between Spot and Perp prices (Funding Rate).
*   **Economic Value**: Keeps the Perp price pegged to the Spot price, ensuring market efficiency.

**10. Digital Asset Treasury ("The Flywheel")**
*   **The Hook**: A decentralized "ETF" that continuously uses revenue to buy back EGLD.
*   **Economic Value**: Programs the "Number Go Up" technology directly into a smart contract interaction.

### High-Risk / "Degen" Strategies

**11. Leveraged Yield Farming ("The Degen Box")**
*   **The Hook**: Borrow against lsEGLD to farm high-APY speculative pools.
*   **Economic Value**: Bootstraps liquidity for new, smaller projects (though high risk).

**12. Leveraged Yield Farming with AI Optimization ("The Guardian")**
*   **The Hook**: Leverage with an AI co-pilot that manages liquidation risk 24/7.
*   **Economic Value**: Reduces the "Bad Debt" risk of the system while maintaining high-octane yields.

**13. Casino Bankroll ("The Whale")**
*   **The Hook**: Provide liquidity to on-chain GambleFi protocols.
*   **Economic Value**: Captures the "House Edge" (1-3%) from gambling volume, a high-velocity sector.

**14. High-Leverage Options Vaults ("The Oracle")**
*   **The Hook**: Vaults that automatically write (sell) covered calls/puts.
*   **Economic Value**: Monetizes volatility.

**15. Arbitrage & MEV ("The Hunter")**
*   **The Hook**: Bots that align prices across DEXes.
*   **Economic Value**: Ensures global price consistency, making the chain reliable for aggregators.

---

## Strategy Comparison Matrix

| Strategy | Risk | TVL Impact | Velocity | EGLD Growth Score |
| :--- | :--- | :--- | :--- | :--- |
| **New Capital Boost** | Med | High | High | 9 |
| **CLOB Market Making** | Low | Med | Max | 8 |
| **Perpetual Vault** | Med | High | High | 10 |
| **Leveraged Staking** | High | High | Med | 9 |
| **RWA Yields** | Low | High | Low | 8 |
| **Yield Stripping** | Med | Med | Med | 6 |
| **Delta-Neutral** | Low | High | High | 7 |
| **Digital Asset Treasury** | Med | Med | Med | 10 |
