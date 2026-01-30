# Technical Specifications: The 5 Genesis Pools

To ensure the Accelerator DAO creates a "Canonical" DeFi economy, each strategy is built on specific, high-efficiency technical primitives.

## 1. The Magnet (Imported Capital)
*   **Asset Pair**: `lsEGLD / USDC`
*   **Technical Setup**: **Concentrated Liquidity Market Maker (CLMM)**.
*   **Implementation**: **xExchange (V3 Concentrated Liquidity)**.
*   **Logic**: High capital efficiency by concentrating liquidity around the current price. 
    *   **Fees**: 0.3% standard fee tier.
    *   **Fee Switch**: 0.05% of the total volume is routed to the **AcceleratorDAO**.
    *   **Composability**: Magnet LP tokens are whitelisted as **Collateral in Lending Protocols**.
*   **Role**: Primary entry point for stablecoin value into the EGLD ecosystem.

## 2. The Accumulator (Staking Depth)
*   **Asset Pair**: `lsEGLD` (Single Sided), plus `lsEGLD/USDC` and `EGLD/lsEGLD` LP Tokens.
*   **Technical Setup**: **Automated Leveraged Staking Vault**.
*   **Implementation**: Integration with **Lending Protocols**.
*   **Logic**: The vault takes `lsEGLD`, borrows `EGLD` (or more `lsEGLD`), and loops the position up to 3x-5x leverage.
    *   **Dependency**: Success depends on **The Anchor**; deep liquidity in EGLD/lsEGLD is required to ensure users can borrow and swap with minimal slippage during the loop.
*   **Role**: Maximizes the Network Staking Ratio by turning 1 EGLD of capital into 3 EGLD of staked weight.

## 3. The House (Perps Liquidity)
*   **Asset Pair**: `USDX Vault` (LP index for Perp Counter-party)
*   **Technical Setup**: **Multi-Asset Oracle-Based LP Vault**.
*   **Implementation**: **Hyperliquid (HLP) Architecture** (Target).
*   **Logic**: Users deposit **lsEGLD**, **USDC**, or **LP Tokens** (Magnet/Anchor). The system internally mints **USDX** to track positions and PnL.
    *   **Yield**: LPs earn 70-100% of trader losses and 100% of trading fees.
    *   **Safety**: Oracle-based pricing prevents flash-loan liquidations.
    *   **Innovation**: Accepting LP tokens as Perp liquidity allows LPs to maintain trade fee exposure in DEXs while acting as the house in Perps.
*   **Role**: Provides deep liquidity for high-leverage trading without traditional order books.

## 4. The Anchor (Peg Stability)
*   **Asset Pair**: `EGLD / lsEGLD`
*   **Technical Setup**: **StableSwap (Dynamic Invariant)**.
*   **Implementation**: Standard StableSwap model with a protocol-read rate.
*   **Logic**: The invariant/exchange rate is **read directly from the LiquidStaking Contract**. 
    *   **Dynamic Value**: Since `lsEGLD` accumulates rewards daily, the EGLD value of 1 `lsEGLD` is always growing. The pool adjusts its internal price to match this on-chain reality.
    *   **Composability**: Anchor LP tokens can be used as **Collateral in Lending Protocols**.
*   **Role**: Guarantees that users can exit Liquid Staking back to EGLD instantly at any scale.

## 5. The Bond (Yield Stripping)
*   **Asset Pair**: `lsEGLD` (Principal + Yield)
*   **Technical Setup**: **Yield Tokenization (PT/YT)**.
*   **Implementation**: Similar to Pendle Finance.
*   **Logic**: Splits `lsEGLD` into a **Principal Token (PT)** (fixed value) and a **Yield Token (YT)** (claims all future staking rewards).
*   **Role**: Creates a Fixed-Income market for conservative investors (buying PT at a discount) and a Yield Speculation market for degens (buying YT).
