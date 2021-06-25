# Manual Investment

## Investment Explanation

The type of investments treated by Deunifi DApp are those that use the UNI-V2 LPs tokens as collateral in MakerDAO vaults. 

The UNI-V2 collateral is locked in the MakerDAO vault and is borrowed DAI.

With the borrowed DAI are obtained more UNI-V2 LPs tokens, that again are locked in the vault, to get more DAI, and continues until is reached the desired APY/collateralization ratio.

In this kind of investments, as we are going see in the example below, are required a lot of transactions to achieve them.

Obviously each transaction has a cost, and more transactions means higher costs.

## An Example

### Do Investment

Lets show a simplified example following the manual steps to achieve this kind of investments.

Suppose we have 10 ETH and we want to invest in UniswapV2 ETH/USDT liquidity pool.

Let's suppose that the APY for this liquidity pool is 30% \(the APY can be calculated using the information provided by the [UniswapV2 Analytics](https://v2.info.uniswap.org/home)\).

And let's suppose the ETH price is 2000 USD.

We begin with the first steps:

1\) Swap 5 ETH for 10000 USDT \(now we have 5 ETH and 10000 USDT\).

2\) Approve UniswapV2 to use our USDT token \(this step is required only once for each token to use\).

3\) Add liquidity \(5 ETH and 10000 USDT\) to the UniswapV2 ETH/USDT liquidity pool. After adding liquidity we receive an amount X of UNIV2ETHUSDT tokens.

{% hint style="info" %}
The X amount of UNIV2ETHUSDT tokens have initially a value of 20k USD. Why? Because we need them to recover the deposited liquidity in UniswapV2 ETH/USDT liquidity pool \(our 5 ETH and 10000 USDT\).
{% endhint %}

> Let's analyze the status until now. 
>
> We own X amount of UNIV2ETHUSDT tokens, and its value is 20000USD.
>
> Our gain in a year will be 30% of 20000 USD = 6000 USD.

We are going to continue with the next steps and see what happens.

4\) Create our MakerDAO proxy to manage MakerDAO vaults \(this step is required only once\).

5\) Create our MakerDAO UNIV2ETHUSDT-A vault type \(this step is required only once per vault type\).

6\) Approve our proxy to use our UNIV2ETHUSDT token \(this step is required only once for each token to use\).

> The liquidation ratio in UNIV2ETHUSDT-A vault type at the time of writing is 140%. This means that we can generate initially in our example a maximum debt of 20000 USD/1,4 =~ 14285 DAI.
>
> Why? Because the value of our collateral \(20000 USD\) is 40% more that the debt to be generated \(14285 DAI\).
>
> We are supposing there is no problem to generate the maximum debt, but please be advice that in real scenario your vault may be liquidated, applying the corresponding penalties.

7\)  Take our X amount of UNIV2ETHUSDT and lock it in a MakerDAO UNIV2ETHUSDT-A vault type, and borrow 14285 DAI from our vault. We leave our vault with 140% of collateralization ratio \(the limit\).

Great, now we have DAI. The idea here is to swap half of the DAI for ETH, and the other half for USDT.

8\) Approve UniswapV2 to use our DAI token \(this step is required only once for each token to use\).

9\) Swap 7142.5 DAI for 3.57125 ETH \(remember that ETH price is 2000 USD\).

10\) Swap 7142.5 DAI for 7142.5 USDT \(1 DAI = 1 USDT\).

11\) Add liquidity \(3.57125 ETH and 7142.5 USDT\) to the UniswapV2 ETH/USDT liquidity pool \(after adding liquidity we receive an amount Y of UNIV2ETHUSDT tokens\).

> Let's analyze the status until now. 
>
> We own \(X+Y\) UNIV2ETHUSDT tokens, and its value is \(20000 USD + 14285 USD = 34285 USD\), and we have a debt of 14285 DAI.
>
> The debt in a UNIV2ETHUSDT-A vault type has an annual stability fee of 4 %.
>
> Now, What is the new APY? Well, our gain in a year will be 30% of 20000 USD + \(30% - 4%\) of 14285 USD = 9714.1 USD. Then our new APY is \(9714.1/20000\)\*100 = 48.5705%

If we stop here, and lock our Y amount of UNIV2ETHUSDT tokens in our vault \(to avoid liquidation\), we will have a collateralization ratio of \(34285 USD/14285 USD\)\*100 = 240%, and our APY will be improved from 30% to 48.5705%.

But lets say that we want to stop at a collateralization ratio of 200%.

Well, we continue the steps to achieve this:

12\) Take our Y amount of UNIV2ETHUSDT and lock it in our vault, and borrow the necessary DAI \(20000 DAI - 14285 DAI = 5715 DAI\) to achieve a final collateralization ratio of 200%. 

{% hint style="info" %}
A 200% collateralization ratio means that our collateral locked has twice the value of our debt. In our example we begin with 20000 USD of collateral, then, if we borrow 20000 DAI and get the equivalent collateral, we are going to have 40000 USD in collateral and 20000 DAI in debt: a 200% collateralization ratio.
{% endhint %}

Great, now we have more DAI. The idea here is to swap half of the DAI for ETH, and the other half for USDT.

13\) Swap 2857.5 DAI for 1.42875 ETH \(remember that ETH price is 2000 USD\).

14\) Swap 2857.5 DAI for 2857.5 USDT \(1 DAI = 1 USDT\).

15\) Add liquidity \(1.42875 ETH and 2857.5 USDT\) to the UniswapV2 ETH/USDT liquidity pool \(after adding liquidity we receive an amount Z of UNIV2ETHUSDT tokens\).

16\) Finally we lock our Z amount of UNIV2ETHUSDT into our vault.

> Let's analyze final status. 
>
> We own \(X+Y+Z\) UNIV2ETHUSDT tokens, and its value is \(20000 USD + 14285 USD + 5715 USD= 40000 USD\), and we have a debt of 14285 DAI + 5715 DAI = 20000 DAI.
>
> Remember that the debt in a UNIV2ETHUSDT-A vault type has an annual stability fee of 4 %.
>
> Now, What is the new APY? 
>
> Well, our gain in a year will be 30% of 20000 USD + \(30% - 4%\) of 20000 USD = 11200 USD. Then our new APY is \(11200/20000\)\*100 = 56%

### Undo Investment

Obviously, to undo the investment given in the example, are necessary a similar quantity of transaction that involves the process of: 

* Remove UNIV2ETHUSDT collateral from the vault \(the amount to remove is limited by the liquidation ratio\).
* Use this collateral to remove ETH and USDT from the liquidity pool.
* Swap ETH to DAI.
* Swap USDT to DAI
* Pay part of the debt.

This steps are repeated until the debt is completely paid.

### Analysis

As we can see, are required a lot of transactions to achieve this kind of investments.

Obviously each transaction has a cost, and more transactions means higher costs.

In this example we only do 3 iterations to achieve the final results, but there are other vault types that permits to have lower collateralization ratio, and this means more iterations.

{% hint style="info" %}
At the time of writing, when doing an investment in a UNIV2DAIUSDC-A vault, it is possible to use only 1k USD to have an investment of 40k USD. This improves a lot the expected APY.

The number of iterations in this case is more than 40 \(in our example above were only 3\). This is practically impossible to achieve doing manual steps.
{% endhint %}

## Solution

To solve the problem of multiple transactions and high costs, Deunifi provides a solution to achieve the same results using one and only one transaction. All of this with a predictable final state after the transaction is executed.

