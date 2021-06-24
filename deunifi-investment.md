# Deunifi Investment

## How It Works?

Basically, when you do an investment using Deunifi App happens the following:

* You define the amount of UNI-V2 collateral to be lock in your vault.
* You define the amount of each token involved in the operation to use from your account.
* And optionally you define the tolerance for the transaction \(If transaction conditions are modified beyond tolerance, then the transaction will be rejected\) assuring that the final result it is what you expect.

Thats it.

## An Example

Lets do the same investment that was made in the previous section.

### Investing

In the example of the previous section, we suppose that we have initially 10 ETH, and that we want to invest in UniswapV2 ETH/USDT liquidity pool.

The APY for this liquidity pool is 30%. And ETH price is 2000 USD.

The result we want to achieve is an investment of 40000 USD in ETH/USDT liquidity pool, with a debt of 20000 DAI \(meaning a collateralization ratio of 200%\)

The steps to invest using Deunifi are the following:

1\) Create our MakerDAO proxy to manage MakerDAO vaults \(this step is required once and only once, and it is not required if you already have a proxy\).

2\) Create our MakerDAO UNIV2ETHUSDT-A vault type \(this step is required only once per vault type, and it is not required if you already have the vault type\).

3\) We define that we want to lock 10 ETH and 20000 USDT, and that we are going to use 10 ETH from our account. Deunifi DApp is going to display the expected collateralization ratio, expected APY, and other indicators. Then we decide to do the transaction.

The steps 1\) is done once and only once. Once we have our proxy, we do not need to perform this step again for future investments.

The step 2\) is done only once per vault type. Once created the vault for an specific collateral type, we keep using the same vault for future investments.

So, as we can see, the third step is the transaction that integrates all the iterations and its transactions of the manual investment steps, using one and only one step.

> Exceptionally, in case we want to use some token instead of ETH, it is needed to approve our proxy to use this token.

{% hint style="info" %}
This is not only a lot easier, the results are predictable, and the investment costs are lower too.
{% endhint %}

### Removing the investment

Removing the investment is performed in one step too. It requires to define:

* The amount of debt that we want to pay.
* Optionally, the amount of DAI that we want to use from our account.
* The amount of debt to be payed using token0 \(in our example ETH\).
* The amount of debt to be payed using token0 \(in our example USDT\).
* The UNI-V2 collateral amount to free from our vault.
* The UNI-V2 collateral amount to remove from liquidity pool to receive token0 and token1 \(in our example ETH and USDT\).

> Exceptionally, in case we want to use DAI from our account, it is needed to approve our proxy to use this token once and only once.

After defining this parameters, are displayed the final vault status indicators, the amount of UNI-V2 to receive, the amount of token0/token1 to receive, and other indicators.

Then we can perform the transaction.

{% hint style="info" %}
Again, this is not only a lot easier, the results are predictable, and the investment costs are lower too.
{% endhint %}

## Fees

The involved fees are the following:

* **AAVE Flash Loan Fee:** This is the fee required to get the Flash Loan to achieve the investment transaction in only one operation. At the time of writing this documentation the fee is 0,09 % of the Flash Loan amount \(the amount generally is the debt to generate in vault or the debt to payback\).
* **Deunifi Service Fee:** This fee is to support the development team that created and maintains Deunifi DApp. At the time of writing the fee is 0,1 % of the debt generated or cancelled.

In our example the fees for the investment transaction would be:

* **AAVE Flash Loan Fee:** 10000 DAI \* 0,09/100 = 9 DAI
* **Deunifi Service Fee:** 10000 DAI \* 0,1/100 = 10 DAI

So the fees total amount would be 19 DAI.

To remove investment operation for our example the fees total amount would be 19 DAI too.

The fees are displayed in the transaction summary for each operation in the Deunifi DApp. 

## Security

To reduce at minimum risks regarding security, Deunifi was build to do not have to store any asset, and to not need any special authorization.

All the assets of your investment are stored in MakerDAO vaults. In fact, once it is performed a transaction with Deunifi, you can inmediately view the result using the MakerDAO DApp.

Additionally, all the token approvals are made only for your proxy.

All the operations performed are done using your proxy.

