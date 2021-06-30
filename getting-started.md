# Getting Started

## Connecting

First of all to perform an investment using Deunifi, you must connect using Metamask.

{% hint style="info" %}
At the time of writing we are supporting only Metamask, but we are working to integrate more wallets to our App.
{% endhint %}

![Connect button](.gitbook/assets/image%20%2816%29.png)

## Proxy Creation

To perform any transaction in Deunifi, it is used the MakerDAO proxy associated with the connected account.

If you already own a proxy in MakerDAO you can skip this section

{% hint style="info" %}
If you own a proxy in MakerDAO, then the Deunifi App it is going to automatically recognize your proxy, and the 'CREATE PROXY' button will disappear.
{% endhint %}

{% hint style="info" %}
The proxy creation it is done only once. Once created, it is used that proxy for all the transactions done in Deunifi App. 
{% endhint %}

The proxy creation it is very simple. You only need to click the 'CREATE PROXY' button:

![](.gitbook/assets/image%20%2819%29.png)

Then you have to confirm the Metamask's popup with the transaction details:

![](.gitbook/assets/image%20%2817%29.png)

{% hint style="info" %}
Remember that to perform any transaction in the Ethereum network you are going to need ETH.
{% endhint %}

After the transaction is confirmed, you can access to it in Etherscan clicking 'VIEW TRANSACTION' button. Additionally, once the transaction is confirmed, after a few seconds, the 'CREATE PROXY' button will disappear and the 'CREATE VAULT' button will be available:

![](.gitbook/assets/image.png)

## Vault Creation

To perform a transaction with Deunifi, first you need to have a vault. 

The vault to be created depends on the kind of investment you want to have.

{% hint style="info" %}
Checkout our [Vault Classification](core-concepts/vault-classification.md) section to understand better the different kinds of vaults.
{% endhint %}

{% hint style="info" %}
If you already own a MakerDAO vault type supported by the Deunifi App, you can skip this section.
{% endhint %}

Once defined the vault type to be created, simply select it from the drop down box, and click on 'CREATE VAULT' button.

![](.gitbook/assets/image%20%2813%29.png)

Then, confirm the Metamask popup to send the transaction.

Once the transaction is confirmed in the network, after a few seconds, the Vault drop down is going to change automatically displaying the vault created for your account.

A link to checkout your recent created vault in Oasis App, is going to be displayed instead of the 'CREATE VAULT' button. 

![](.gitbook/assets/image%20%2811%29.png)

{% hint style="info" %}
Please note that you can create more than one vault for same vault type in case you need it.
{% endhint %}

## Lock And Draw

Lock And Draw is the operation that let us do an investment in only one operation.

We only need to specify how much collateral we want to lock and how much debt we want to get.

We can use ETH or tokens from our account.

The tokens available to use are:

* Both tokens that compose the UniswapV2 pair liquidity pool where we are going to invest.
* The UNI-V2 token corresponding to the liquidity pool.
* DAI token.

In the following sections we are going to show some examples to understand better how to do an investment.

### UNIV2DAIETH-A Using ETH

In this example we are going to invest in a UNIV2DAIETH-A vault using only ETH.

We are using here an ETH price of 1977 DAI/ETH \(approximately\).

Let's suppose we own 10 ETH and want to have an investment in UNIV2DAIETH-A with a 200% collateralization ratio.

Well this is very easy to achieve:

![](.gitbook/assets/image%20%282%29.png)

* We set  the 'ETH To Lock' to 10 ETH \(the 'DAI to lock' automatically change to the equivalent 10 ETH value in DAI\).
* Then we set the ETH amount we want to use from our account: 10 ETH.

The expected result of the transaction is displayed in two places:

* Vault Status section: 
  * In black are displayed the current values
  * In blue are displayed the expected values after performing the transaction.
* Transaction Summary section:
  * Are displayed the expected values for the vault indicators, and for some of them, their corresponding tolerance \(min. or max.\).
  * Are displayed the transaction fees \(this fees are already considered when calculated the expected values\).

There are some key indicator to mention from the Transaction Summary section:

* Collateral to Lock: 
  * It is the expected total value to invest in UNIV2DAIETH liquidity pool and locked into our vault.
  * In this example the expected total value to invest is 39960 USD \(and we only using from our account 10 ETH that are equivalent to 19770 USD\)
* Dai to Draw:
  * It is the debt generated in our vault to achieve an investment with higher value than the investment we can actually have using only the assets we own.
* Expected collateralization ratio:
  * Is the expected percentage relation between the value of the collateral to lock \(in USD\) and the debt generated in our vault
* Expected liquidation price:
  * Is the collateral price that generates the liquidation of our vault.
* Expected Vault's APY:
  * It is an estimation of the vault's APY based on information of last X days obtained from Uniswap's Analytics.
  * In this case the estimated UNIV2DAIETH liquidity pool APY \(based in the last 30 days\) is 22% \(this information is displayed in Vault Status section\)
  * And the vault's APY estimation is 41% \(why? because we are improving the APY investing twice of our actual assets and taking a debt to achieve this\).
* Flash Loan Fees:
  * The fees payed to get the flash loan to achieve this operation in only one transaction.
  * At the time of writing the fees are 0.09% of the flash loan value.
* Deunifi Service Fee:
  * Fees for the development team to maintain and give support for the Deunifi App.
  * At the time of writing the fees are 0.1% of the draw DAI. 

{% hint style="info" %}
You can play around with different values and check the expected results in the Vault Status and in the Transaction Summary sections.
{% endhint %}

To understand better the different indicators in the Vault Status and Transaction Summary sections, please check out [Vault Status Indicators](core-concepts/vault-status-indicators.md).

Finally to perform the transaction it needed to click on LOCK AND DRAW button.

Before and after the transaction is confirmed, you can access to it in Etherscan.

Additionally, once the transaction is confirmed, after a few seconds, the Vault Status section is going to  change to show its new status.

![](.gitbook/assets/image%20%2822%29.png)

Another tab is going to be displayed next to 'LOCK AND DRAW' tab:

![](.gitbook/assets/image%20%289%29.png)

The WIPE AND FREE operation let you to remove your investment and recover your tokens.

You can learn more about this operation in the [Wipe And Free](getting-started.md#wipe-and-free) section.

### UNIV2USDCETH-A Using USDC and ETH

In this example we are going to invest in a UNIV2USDCETH-A vault using 50% USDC and 50% ETH.

We are using here an ETH price of 1977 USD/ETH \(approximately\).

Let's suppose we own 5 ETH and 10000 USDC and want to have an investment in UNIV2DAIETH-A with a 200% collateralization ratio \(approximately\).

To achieve this:

![](.gitbook/assets/image%20%2814%29.png)

* We set  the 'ETH To Lock' to 10 ETH \(the 'USDC to lock' automatically change to the equivalent 10 ETH value in USDC\).
* Then we set the USDC amount we want to use from our account: 10000 USDC.
* Then we set the 5 ETH amount we want to use from our account: 5 ETH.

As we can see the LOCK AND DRAW button is not available. That happens because we need to approve our proxy to use our USDC tokens \(the approval transactions are performed only once per token\).

We click in APPROVE USDC, and send the approval transaction with Metamask.

Once confirmed the approval transaction the APPROVE USDC button is going to disappear and the LOCK AND DRAW button it is going to be enabled.

![](.gitbook/assets/image%20%284%29.png)

Then we click in LOCK AND DRAW and after the transaction is confirmed we get the following Vault Status:

![](.gitbook/assets/image%20%2820%29.png)

### UNIV2WBTCDAI-A Using UNIV2WBTCDAI

In this example we are going to invest in a UNIV2WBTCETH-A vault using UNIV2WBTCDAI token.

This case generally is useful when you already have an investment in Uniswap V2 liquidity pool and you want to create a leverage in that investment.

We are using here a WBTC price of 34082 USD/WBTC \(approximately\).

Let's suppose we own 10000 USD in UNIV2WBTDAI token and we want to have an investment with a 200% collateralization ratio \(approximately\).

To achieve this:

![](.gitbook/assets/image%20%285%29.png)

We set  the 'DAI To Lock' to 5000 DAI \(the 'WBTC to lock' automatically change to the equivalent of 5000 DAI in WBTC\).

Then we set the 'UNI-V2 to use' amount to 0.0002531 UNIV2WBTCDAI \(approximately 10000 USD\).

As we can see the LOCK AND DRAW button is not available. That happens because we need to approve our proxy to use our UNIV2WBTCDAI tokens \(the approval transactions are performed only once per token\).

We click in APPROVE UNI-V2, and send the approval transaction with Metamask.

Once confirmed the approval transaction the APPROVE UNI-V2 button is going to disappear and the LOCK AND DRAW button it is going to be enabled.

Then we click in LOCK AND DRAW and wait for the transaction to be confirmed.

### UNIV2WBTCETH-A Using WBTC and ETH

In this example we are going to invest in a UNIV2WBTCETH-A vault using ETH and DAI.

We are using here an ETH price of 1977 USD/ETH, and a WBTC price of 34082 USD/WBTC \(approximately\).

Let's suppose we own 6.1 ETH and 9000 DAI and want to have an investment in UNIV2WBTCETH-A with a 300% collateralization ratio \(approximately\).

To achieve this:

![](.gitbook/assets/image%20%2826%29.png)

We set  the 'ETH To Lock' to 8 ETH \(the 'WBTC to lock' automatically change to the equivalent 8 ETH value in WBTC\).

Then we set the 'ETH to use' amount we want to use from our account: 6.1 ETH.

Then we set the 'DAI to use' amount we want to use from our account: 9000 DAI.

As we can see the LOCK AND DRAW button is not available. That happens because we need to approve our proxy to use our DAI tokens \(the approval transactions are performed only once per token\).

We click in APPROVE DAI, and send the approval transaction with Metamask.

Once confirmed the approval transaction the APPROVE DAI button is going to disappear and the LOCK AND DRAW button it is going to be enabled.

Then we click in LOCK AND DRAW and wait for the transaction to be confirmed.

### UNIV2DAIUSD-A: x40 Investment

In this example we are going to invest in a UNIV2DAIUSDC-A vault.

This is a special case because we are going to use only 1000 USDC from our account to create a 40000 USD investment.

To achieve this:

![](.gitbook/assets/image%20%2815%29.png)

We set  the 'USDC To Lock' to 20000 USDC \(the 'DAI to lock' automatically change to the equivalent value in DAI\).

Then we set the 'USDC to use' amount we want to use from our account: 1000 USDC.

We can verify that in the Transaction Summary section that the Collateral to lock has a value of 39852 USD \(near x40 the value we are using from our account\).

But, we have an error. The Expected Collateralization Ratio it is above the Liquidation Ratio \(102%\), but the Min. Expected Collateralization Ratio is below 102%.

To solve this, we are going to change the [Slippage Tolerance](getting-started.md#tolerance-and-deadline) from 1% to 0.1%. And we are doing this here because we are treating only with stable coins, so there risk that the conditions are changed, and the transaction be reverted, are very low.

![](.gitbook/assets/image%20%287%29.png)

Then we click in LOCK AND DRAW and wait for the transaction to be confirmed.

## Tolerance and Deadline

If we compare the final Vault Status showed in the [first example](getting-started.md#univ-2-daieth-a-using-eth), with the status before performing the transaction, we are going to realize that there are some little differences.

This is normal, because the transactions in blockchain are not written immediately, so, some conditions can change between the moment that it is sent the transaction, and the moment that it is confirmed the transaction \(the difference between this two moments could be seconds, minutes, hours, or even days\).

To avoid performing a transaction that result in the partial lost of our investment, there are two important parameters to take into account:

* Slippage Tolerance:
  * This is the maximum error percentage admitted in the transaction operations.
  * Modifying it will result in a lower or higher difference between the expected results and its minimum and maximum limits.
  * When are executing the transaction in the blockchain, if its results do not correspond to this minimum or maximum expected limits, then the transaction will be reverted.
  * The default value is 1%.
* Transaction deadline:
  * This is the time limit to confirm the transaction in the blockchain since it was sent to be executed.
  * This value is specified in minutes.
  * In case the transaction be executed after this time limit, then it will be reverted.
  * The default value is 120 minutes.

This parameters are enabled activating the 'Display additional options' button:

![](.gitbook/assets/image%20%2818%29.png)

{% hint style="info" %}
A reverted transaction means that no modifications are done. Your token balances remains the same, and your vault status remains the same. No modifications are done.
{% endhint %}

{% hint style="success" %}
Reverting a transaction is a security measure to assure that we are not getting unexpected results if the transaction conditions in the blockchain change beyond a defined limit.
{% endhint %}

{% hint style="warning" %}
The lower the tolerance and deadline, then the higher the probability that the transaction to be reverted.

Reverted transactions also consume gas, and gas is paid with ETH. Then, tolerance and deadline should define acceptable limits, but assuring transaction to not be reverted.
{% endhint %}

You can play around with this parameters and check how the expected result limits are modified.

## Wipe And Free



