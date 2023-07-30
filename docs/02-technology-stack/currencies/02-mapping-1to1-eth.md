# Launch currency with 1:1 mapping of ERC-20

When defining a currency it can be mapped to an ERC-20 1:1. The currency on Verus and the ERC-20 on Ethereum are then always interchangeable 1 to 1. 

::: tip ↔️ Verus-Ethereum Bridge ⚠️ For Testnet!
The Verus-Ethereum testnet bridge is the first of its kind. All tokens and currencies flowing over the bridge are never in anyone’s custody, and are proven and verified by consensus rules.

[👉 Access the Verus-Ethereum Testnet Bridge](https://ethbridge.verustest.net/) (⚠️ Goerli testnet)
:::

::: warning Need help setting up a currency launch? 🤔
[👉 Go to the Verus Discord #pbaas-development channel. The community is happy to assist!](https://www.verus.io/discord)
:::

### Defining the currency
To create a currency of a specific name, we need a VerusID of the same name. The controller of this VerusID is the only one who can create a currency of that name, and we can only do so once.

The cost for a VerusID on the Verus testnet is ``100 VRSCTEST`` (or 80 when using a referral). The cost to launch a currency is ``200 VRSCTEST``. Before launching we need to have enough VRSCTEST in the namespace VerusID.

In our example we have a namespace ``MyUSDC`` with which we want to launch a currency that is mapped to the Ethereum ``USDC`` ERC-20 (on Goerli testnet, [see contract address](https://goerli.etherscan.io/address/0x98339D8C260052B7ad81c28c16C0b98420f2B46a)).

Below is the command to map a currency 1:1 to an ERC-20 on Ethereum. The ``address`` field is the Ethereum smart contract address of the ERC-20 we want to map to.

``` json
./verus -chain=VRSCTEST definecurrency '{
    "name":"MyUSDC", 
    "options":32, 
    "systemid":"veth", 
    "parent":"vrsctest", 
    "launchsystemid":"vrsctest", 
    "nativecurrencyid":{
        "type":9, 
        "address":"0x98339D8C260052B7ad81c28c16C0b98420f2B46a"
    },  
    "initialsupply":0, 
    "proofprotocol":3
}'
```

After we put in the command, we get returned a HEX. We use this HEX to launch the currency on the network. Use the command below to launch the currency:

``` json
./verus -chain=VRSCTEST sendrawtransaction "HEX"
```

Now we have to wait a few blocks for the currency to be available on the network. 

### Export to Ethereum
The last step is to export the currency to Ethereum so we can see it there too. [👉 Read it here](/definecurrency/export-to-eth/)
