# Test Network

It is possible possible to test how Deunifi works without using real ETH or real tokens.

This can be achieved [connecting to the Kovan network](test-network.md#connecting-to-kovan) instead of the Mainnet network.

Please, be advice that there are some [limitations](test-network.md#limitations) regarding using Deunifi in the Kovan Test Network.

To get some ETH you can use the [Kovan Fauset Service](test-network.md#kovan-fauset-service).

## Limitations

There exists some limitations in the Kovan test network, mainly caused by the protocols in which Deunifi based its core functionality.

### Vault Type Limitation

At the time of writing, the only available vault type in MakerDAO is the UNIV2DAIETH-A.

As Deunifi depends on the MakerDAO vault types, then UNIV2DAIETH-A is the only vault type in Deunifi too.

So you can only perform tests for this vault type.

### Price Inconsistencies

Deunifi depends on prices on MakerDAO and UniswapV2 protocols.

The problem in Kovan network is that the prices published by MakerDAO are not in sync with the corresponding prices on UniswapV2 protocol.

This leads to inconsistencies for values like 'Collateralization Ratio' and 'Liquidation Price', that generate a vault status that does not make sense in a real scenario.

The following example show this inconsistencies:

![](.gitbook/assets/image%20%2831%29.png)

It is possible to see above that:

* We are locking 1 ETH and 774 DAI \(green arrows\):
  * It is clear that the price of ETH in UniswapV2 is 774 DAI/ETH.
  * So the collateral value locked should be 2 x 774 USD = 1548 USD
* We are using 1 ETH from our account \(orange arrow\):
  * So the collateralization ratio should be around 200%
* But the collateral's current price in MakerDAO is not in sync with the UniswapV2 price \(blue arrow\):
  * The value of the collateral locked in MakerDAO is 3184 USD \(a lot more than 1548 USD\)
  * Then, the collateralization ratio registered is greater than 200%. It is 410% \(red arrow\).

This inconsistencies are caused mainly because prices between protocols are not in sync in the Kovan network.

## Kovan Fauset Service

Kovan Faucet Service let you get some ETH for free in the Kovan test network.

You can access to the following link, login with one of the available options, and write the address where you want to receive ETH:

{% embed url="https://gitter.im/kovan-testnet/faucet" %}

Please be advise, that sometime the service is not working as expected, and have some delays to complete the ETH transfer to your account.

## Connecting To Kovan

First of all, it is a good practice to use different accounts between different networks, to avoid performing transactions in Mainnet, believing that you are connected to a test network.

To create another account in Metamask simple open Metamask, select the menu button, and then the create account option:

![](.gitbook/assets/image%20%2826%29.png)

Connecting to the Kovan network is really simple.

Open Metamask and click on the network selection box:

![](.gitbook/assets/image%20%2838%29.png)

Then select the option corresponding to Kovan network:

![](.gitbook/assets/image%20%2839%29.png)

That's it, now Metamask is going to work with Kovan test network, instead of Mainnet.

Then you can enter to Deunifi App, and connect to it using the connect button.

{% embed url="https://app.deunifi.org/" %}

After establish connection with Deunifi App, you can begin to test it in Kovan network.

