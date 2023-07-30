# Export currency to Ethereum (as ERC-20)

A currency on Verus (testnet) can be exported to Ethereum as an ERC-20 (Goerli testnet). The currency can then be used in the complete Ethereum ecosystem, and on the Verus network. Sending to and from Verus and Ethereum couldn't be easier. 

::: tip ↔️ Verus-Ethereum Bridge ⚠️ For Testnet!
The Verus-Ethereum testnet bridge is the first of its kind. All tokens and currencies flowing over the bridge are never in anyone’s custody, and are proven and verified by consensus rules.

[👉 Access the Verus-Ethereum Testnet Bridge](https://ethbridge.verustest.net/) (⚠️ Goerli testnet)
:::

### Exporting the currency
Now, let’s export a currency from Verus to Ethereum as an ERC-20 over the non-custodial bridge. We must have enough funds to pay for the export. The export fee is: ``~ 0.0504 vETH`` or ``~ 111 VRSCTEST``. These export fees can swing wildly, especially on Goerli testnet.

The command to export a currency to Ethereum Goerli (⚠️) as an ERC-20:

``` json
./verus -chain=VRSCTEST sendcurrency "myVerusID@" '[{
    "address":"0x85a7dE2278E52327471e174AeeB280cdFdC6A68a", 
    "currency":"myCurrency", 
    "amount":0, 
    "exportto":"veth", 
    "exportcurrency":true, 
    "feecurrency":"veth"
}]'
```

Let's break the command down. 

``myVerusID@`` is the from- and change-address. The fee to pay for the export comes from here, and if you paid too much fees the rest will be returned here.

``address`` is the Verus-Ethereum Goerli (⚠️) smart-contract bridge address. Don't change this.

``currency`` is the name of the currency you wish to export as an ERC-20.

``amount`` keep it 0.

``feecurrency`` is the currency the export fees are paid in. Omit this to pay the fees in VRSCTEST.

### Wait for notarization

After the bridge has been notarized to the blockheight where you have exported the currency, you can choose it from the token dropdown on [the testnet bridge website](https://ethbridge.verustest.net/).
