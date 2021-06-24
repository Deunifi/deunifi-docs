# Protocols Involved

## UniswapV2

UniswapV2 is is a decentralized exchange. 

The investments offered by Deunifi are based in some of the liquidity pools \(LPs\) offered in UniswapV2 protocol.

### How LPs Works

Basically an LP offers a mechanism to perform swaps between 2 tokens.

To be possible to perform this swaps, the liquidity pool needs liquidity for each token.

Anyone can add liquidity to a liquidity pool.

When liquidity is added to an LP, it is received in exchange UNI-V2 tokens.

This UNI-V2 tokens represents the value invested in the LP and are needed in case it is desired to remove the investment.

### Benefits of Investing in LPs

When swap operations are performed in LPs, each operation pays a fee \(0,3% of the swapped value for example\).

This fees are distributed between all the liquidity providers proportionally to the amount of liquidity provided to the liquidity pool.

Basically investing in LPs give us the opportunity to own tokens and have a gain for this invested tokens.

{% hint style="info" %}
If you want to understand in more detail how UniswapV2 protocol works, please checkout the [Core Concepts](https://uniswap.org/docs/v2/core-concepts/swaps) in the UniswapV2 official documentation.
{% endhint %}

## MakerDAO

MakerDAO is a decentralized protocol that provides a system of vaults where is possible to lock collateral \(for example ETH, UNI-V2 or some other token\), and take a loan in DAI.

### How Vaults Work

Basically a vault pertains to an specific Ethereum account.

If anyone wants to have a vault the first step is to create it.

A vault has a type of collateral \(ETH, UNI-V2, ...\) that we can lock there.

If we lock collateral, we can borrow DAI up to a certain limit.

This limit is defined by a value called **liquidation ratio** 

The liquidation ratio is a fixed value defined for each vault type, and is de minimal permitted ratio between the relation of collateral locked and the debt in DAI.

{% hint style="info" %}
If you want to understand in more detail how vaults works, please checkout the [Vault Onboarding Guide](https://community-development.makerdao.com/en/learn/vaults/vault-onboarding-guide) in the MakerDAO official documentation.
{% endhint %}

## AAVE

AAVE is a decentralized lending and borrowing protocol.

### Flash Loans

Flash Loans is one of the functionalities offered by AAVE.

The concept is really simple.

Any one can take a loan, for any amount \(for example in DAI\), during an Ethereum transaction execution.

The requirement to take this kind of loan, is to payback the same amount to AAVE, plus the corresponding fees \(0.09% of the loan amount\), before the transaction is finished.

If the loan amount + fees is not payed back, then the transaction is reverted.

{% hint style="info" %}
If you want to understand in more detail how flash loan works, please checkout the [Flash Loans](https://docs.aave.com/faq/flash-loans) section in the AAVE official documentation.
{% endhint %}

