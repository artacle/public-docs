---
description: Experimental digital art index token
---

# AB500 index token

## Introduction

The digital art market has entered a new phase. After a historic wave of on-chain generative art, liquidity has thinned out, attention has fragmented, and it has become harder for both newcomers and veterans to gain diversified exposure to the space.

At the same time, Art Blocks 500 (“AB500”) is a clearly defined cultural and historical set: the complete collection of the first 500 projects released on Art Blocks platform from 2020 to 2025.

Artacle has been tracking AB500 as an index that aggregates the market value of this full set of projects, giving collectors and analysts a clear way to monitor the “Art Blocks 500” as a single benchmark rather than 500 separate markets.

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption><p>AB500 digital art index in USD</p></figcaption></figure>

In this context, Artacle introduces $AB500X, an experimental index token designed to:

* Provide scalable exposure to the Art Blocks 500 index
* Channel trading activity directly into the acquisition of AB500 artworks
* Turn a historically defined collection into a live, community-aligned financial primitive

## Mission

To create the first digital art index token that is economically linked to Art Blocks 500 digital art assets, supports the long-term preservation and growth of this foundational generative art set, and empowers the community to participate in a transparent, liquid, and governance-enabled representation of the AB500 ecosystem.

## Token Overview

| Parameter         | Value                                                                   |
| ----------------- | ----------------------------------------------------------------------- |
| Token Name        | $AB500X                                                                 |
| Underlying        | Artacle AB500 index tracking Art Blocks 500 collections                 |
| Network           | Base                                                                    |
| Launch            | planned Q4 2025                                                         |
| Total Supply      | Defined by total tokens minted during the initial window and then fixed |
| Minting Asset     | $ARTCL                                                                  |
| Mint Window       | One-time, approximately 7 days                                          |
| Initial Liquidity | Bootstrapped by Artacle using 1% of dedicated $ARTCL                    |

During the initial phase, $AB500X will trade freely at market price and is expected to begin at penny-level pricing to encourage broad distribution and real-market testing.

## Phased Development Model

#### Phase 1 — Experimental Launch

* $AB500X initially trades unbound from the numerical value of the AB500 index.
* The aim is to observe natural price discovery, trading behavior, and community adoption.
* Community minting is exclusively available via $ARTCL.
* There is one minting window of \~7 days; after it closes, no further primary minting occurs.
* The Artacle team bootstraps initial liquidity by using 1% of the dedicated $ARTCL buffer to mint initial amount of $AB500X for the liquidity pool.

#### Phase 2 — Synthetic Index Binding

If Phase 1 shows sufficient demand, stability, and ecosystem support, Artacle may:

* Bind $AB500X to the AB500 index via a synthetic mechanism. Market price will be maintained through arbitrage mechanisms via $ARTCL token.
* Optionally introduce leverage or dynamic parameters to amplify index exposure with leverage gradually increasing to 2x, 3x, 4x, 5x and beyond, depending on performance metrics and market conditions.
* Align token economics so that the behavior of $AB500X reflects the performance of the underlying AB500 market more directly.

Details of the synthetic design will be subject to further research and community feedback before activation.

## Minting Mechanics

#### Minting Base: $ARTCL

From day one, $AB500X is minted exclusively using $ARTCL:

* Artacle allocates 1% of a dedicated $ARTCL pool to mint an initial batch of $AB500X for the liquidity pool.
* All additional $AB500X tokens during the mint window are created by community members who spend $ARTCL into the minting contract.

#### One-Time Minting Window

* A single initial minting window is opened for approximately 7 days.
* During this period, any $ARTCL holder can mint $AB500X.
* After the window closes, total supply is fixed and no further primary minting occurs.

### Community Incentives and Airdrops

To strengthen alignment Artacle plans a second $ARTCL airdrop. The distribution is intended to reward:

* Community members with Art Points
* $ARTCL holders
* Liquidity providers supporting $ARTCL

The airdrop structure is designed to:

* Reinforce the role of $ARTCL as the economic base for AB500X
* Reward early adopters who help bootstrap liquidity and awareness
* Stimulate renewed attention toward the AB500 index

## Trading Mechanics and Fee Structure

#### Warm-Up Trading Period

Immediately after trading begins, a warm-up period is activated to:

* Discourage early sniping and short-term extraction
* Rapidly build the NFT index fund backing

Parameters:

* Initial buy fee: 95%, linearly and programmatically decreasing to 10% over approximately 1.5 hours. During this phase, the Artacle team may purchase a certain amount of index tokens bypassing the initial buy fee in order to stabilize the price following the $ARTCL airdrop and the replenishment of the liquidity pool.
* Sell fee: fixed at 50% during the early accumulation phase.

The elevated sell fee remains in place until the AB500 index fund acquires at least:

* 1 × Fidenza
* 1 × Ringer
* 1 × Chromie Squiggle

These three collections serve as initial target milestones for the fund.

#### Standard Fee Structure (Post-Warm-Up)

Once the initial NFT milestones are achieved and the warm-up period ends, the fee structure transitions to a fixed 10% transaction fee on trades, allocated as follows:

| Portion of Fee | Allocation Target                                 |
| -------------- | ------------------------------------------------- |
| 8%             | Purchase of AB500-related NFTs for the index fund |
| 1%             | Art Blocks                                        |
| 1%             | Artacle                                           |

This structure ensures that every trade contributes to expanding and strengthening the underlying AB 500 index and its fund. All token transactions are subject to fees enforced directly at the smart-contract layer via custom Uniswap v4 hooks.

## NFT Acquisition Strategy

#### L1 Bridge Mechanism

To purchase AB500 artworks, 8% of transaction fees are periodically bridged from Base to Ethereum L1, where Art Blocks collections reside.

#### Two Parallel Acquisition Tracks

1. **Market-Cap Push**
   * Accumulate the lowest-priced NFTs across selected AB500 collections.
   * Objective: increase market capitalization and floor stability within the AB500 universe.
2. **Representative Fund**
   * Systematically buy works across a wide spread of AB500 collections, with the aim of reflecting the diversity and structure of the full Art Blocks 500.

From the beginning, the acquisition process will be carried out in a semi-automated way using a multisig account, and later it will be fully automated via smart contracts.

#### Fund Rules

* **No-Exit Policy as a Base Case**\
  By default, NFTs purchased by the index fund are permanently held, they are never listed, sold, or fractionalized. This positions the fund as a long-term, on-chain “vault” for Art Blocks 500 era works.
* **Bull Market Mechanism**\
  In the event of a pronounced digital art bull run, holders will be able to vote on:
  * Selling a portion of the NFT holdings
  * Distributing proceeds as dividends to $AB500X holders
  * It may lead to an increase in the value of $AB500X and enable the acquisition of additional AB500 NFTs.

This document will be updated as new information about the token becomes available.
