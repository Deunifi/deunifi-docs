# Deunifi Benefits

## Impermanent Loss Mitigation

### Impermanent Loss

To understand one of the main benefits of UNI-V2 Collateralized Investments, it is important to understand the concept of Impermanent Loss in UNI-V2 investments.

To put it in few word:

> In essence, impermanent loss is a temporary loss of funds occurring when providing liquidity. It’s very often explained as a difference between holding an asset versus providing liquidity in that asset. Impermanent loss is usually observed in standard liquidity pools where the liquidity provider \(LP\) has to provide both assets in a correct ratio, and one of the assets is volatile in relation to the other, for example, in a Uniswap DAI/ETH 50/50 liquidity pool.
>
> If ETH goes up in value, the pool has to rely on arbitrageurs continually ensuring that the pool price reflects the real-world price to maintain the same value of both tokens in the pool. This basically leads to a situation where profit from the token that appreciated in value is taken away from the liquidity provider. At this point, if the LP decides to withdraw their liquidity, the impermanent loss becomes permanent.

You can access the whole article with detailed explanation [here](https://finematics.medium.com/what-is-impermanent-loss-defi-explained-4375f2df8a9d).

### Mitigation

Why is mitigated the impermanent loss investing in a UNIV2 vault type?

This is because, for example, it is possible to duplicate our investment.

In an UNIV2DAIETH investment, initially we have 50% ETH and 50% DAI. If the price of ETH increases, then we have impermanent loss.

If we duplicate our investment using a UNIV2DAIETH-A vault with a collateralization ratio of 200%, that mean we have initially 100% ETH and 100% DAI of our original investment, so in case ETH price increases, then the impermanent loss will be much lower.

## UNI-V2 Leverage

### Leverage on Fees

Investing in UniswapV2 liquidity pools generate a return fee that is proportional to the invested liquidity.

If we provide a 1% of the total liquidity in a liquidity pool, and let's suppose that the fees from 1 day are 1000 USD in that pool, then we earn 10 USD that day, right?

And what happen if we provide 2% of the total liquidity in the same liquidity pool? Well, we are going to earn 20 USD that day.

Basically, using an UNIV2ETHDAI-A vault with a collateralization ratio of 200%, we achieve this behavior.

{% hint style="info" %}
We are leveraging the returned fees.
{% endhint %}

We can use lower collateralization ratios \(higher debt\) and achieve interesting results.

For example, at the time of writing this documentation, the UNIV2DAIUSDC-A has a liquidation ratio of 102%, and auctions are disabled for this vault type.

This means that we can have a full collateralized vault. If we use only 1000 USD, we can generate an investment in UniswapV2 DAI/USDC liquidity pool of 40000 USD \(x40 our initial investment\). That means x40 of returned fees.

{% hint style="info" %}
Please note that always it is important to consider the vault's stability fee over the generated vault's debt when it is estimated the APY.
{% endhint %}

### Leverage on Token Value

The problem of investing on an UniswapV2 liquidity pool like USDC/ETH for example is that we initially have 50% ETH and 50% USDC of our initial investment.

In case the ETH price increases, we a gain proportionally to a 50% of our initial investment \(to simplify we are not considering impermanent loss\).

But in case we want to invest in UniswapV2 liquidity pool like USDC/ETH, and, at the same time, we are confident that the ETH price will increase, then we can an investment on a UNIV2USDCETH-A vault with a collateralization ratio of, for example, 200%.

In case the ETH price increases, we have a return proportionally to a 100% of our initial investment \(without considering impermanent loss\) and additionally we earn fees from the liquidity pool.

## Security

To reduce at minimum risks regarding security, Deunifi was build to not have to store any asset, and to not need any special authorization.

All the assets of your investment are stored in MakerDAO vaults. In fact, once it is performed a transaction with Deunifi, you can immediately view the result using the MakerDAO Oasis App.

Additionally, all the token approvals are made only for your own proxy.

All the operations performed are done using your proxy.

