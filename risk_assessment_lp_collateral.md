# Risk Assessment: LP Token Collateral & Deep Liquidity Strategy
**Security Analysis Report**

## 1. Executive Summary
**Proposal**:
1.  Establish deep `lsEGLD-EGLD` (Correlated) and `lsEGLD-USDC` (Standard/CLMM) pools.
2.  Allow `lsEGLD-USDC` LP Tokens to be used as **Collateral** in Lending Protocols.

**Verdict**: **HIGH RISK**. Requires strict mitigation parameters.
While architecturally sound for capital efficiency, using Volatile LP Tokens as collateral introduces "Atomic Attack Vectors" that can drain lending pools if not isolated.

---

## 2. Threat Modeling (Attack Vectors)

### Vector A: The "Flash-Crash" Oracle Attack (Critical)
*   **Mechanism**:
    1.  Attacker Flash Loans massive EGLD.
    2.  Dumps EGLD into the `lsEGLD-USDC` pool, crashing the spot price of EGLD/lsEGLD.
    3.  **Result**: The "Total Value" of the LP Token drops instantly (or spikes, depending on the math).
    4.  **Exploit**:
        *   If LP Price *Drops*: Attacker triggers liquidations on innocent users, buying their collateral at a discount.
        *   If LP Price *Spikes* (Manipulation of the `TotalSupply` denominator or `SqrtPrice`): Attacker borrows massively against their own LP collateral (which is now valued at e.g., 2x real value) and defaults.
*   **Vulnerability**: Dependence on "Spot Price" for LP Valuation.

### Vector B: The "IL Death Spiral" (Market Risk)
*   **Mechanism**:
    1.  EGLD price crashes 50%.
    2.  The `lsEGLD-USDC` LP position suffers Impermanent Loss (IL), meaning the LP Token value drops *faster* than holding the assets.
    3.  **Result**: Users who borrowed against this LP Token breach their LTV (Loan-To-Value) faster than expected.
    4.  **Cascading Liquidation**: Liquidators sell the LP Token -> Breaks the Pool Peg further -> More Liquidations.

---

## 3. Required Mitigations (The "Safe Mode" Config)

### Mitigation 1: The Oracle Mandate (TWAP & Fair Price)
DO NOT use Spot Price.
*   **Requirement**: The Lending Protocol MUST use a **Time-Weighted Average Price (TWAP)** (Min 30 minutes) for the underlying `lsEGLD/USDC` valuation.
*   **Fair LP Formula**:
    `Price_LP = (2 * Sqrt(Reserve_A * Reserve_B) * Sqrt(Price_A * Price_B)) / Total_Supply`
    *   *Why*: This formula (Theta/Alpha Homora standard) is resistant to manipulation of the ratio `Reserve_A / Reserve_B`, provided `Price_A` and `Price_B` are secure (Chainlink).

### Mitigation 2: Supply Caps & Isolation
*   **Isolation Mode**: LP Tokens should be an **Isolated Collateral**.
    *   *Meaning*: You can *only* borrow a specific stablecoin (e.g., USDC) against this LP Token. You cannot Cross-Margin it with other risky bets.
*   **Supply Cap**: Limit the Total LP Tokens accepted to **$5M** initially.
    *   *Why*: Limits the "Max Damage" if an exploit occurs.

### Mitigation 3: Conservative LTV
*   **Max LTV**: **60%** (vs 80% for pure EGLD).
    *   *Reason*: Buffer for Impermanent Loss volatility.

---

## 4. Blockchain Developer Perspective (Implementation)
*   **Contract Risk**: Using `lsEGLD` (Liquid Staking) adds a layer of "Smart Contract Risk".
    *   *Scenario*: If the Liquid Staking contract pauses or gets hacked, the `lsEGLD` value effectively goes to 0.
    *   *Impact*: The Lending Protocol Oracle must have a "Kill Switch" to zero out the collateral value if the LST depegs > 10%.
*   **Standard Compatibility**: Ensure the LP Token is a standard ESDT. If it's a "Position NFT" (e.g., Uniswap V3 style), Lending Protocols cannot typically accept it without a custom Wrapper Contract.

## 5. Final Recommendation
**Proceed with Caution.**
1.  **Launch Pool**: `lsEGLD-USDC` (Deep Liquidity).
2.  **Delay Collateral**: Wait until Pool TVL > $10M before enabling it as Lending Collateral (to make manipulation expensive).
3.  **Enforce TWAP**: Hard requirement for the Lending integration.
