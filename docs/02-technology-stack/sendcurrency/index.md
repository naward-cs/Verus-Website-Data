
# Introduction
Verus DeFi is incredibly simple, cheap and MEV-free. You can convert into a currency that has reserves (you are now "providing liquidity"), and you can convert out of the currency again, back into its reserves. [Learn more about basket currencies (DeFi AMMs).](/currencies/#basket-currencies)

| Conversion type | Fee | Fee goes to |
| :-----| :------ | :-------- |
| Basket currency ↔️ reserve | 0.025% | Fee added to reserves of the basket currency | 
| Reserve ↔️ reserve | 0.05% | 0.025% added to reserves of the basket currency, 0.025% to the block reward for miners and stakers |

## Sendcurrency command
With the ``sendcurrency`` command you can send and convert currencies (also cross-chain).

## L1 DeFi
Verus is a ``UTXO-based`` blockchain with ``smart transactions``. All smart capabilities are implemented on the protocol level. This has many advantages over blockchain projects that use layer two solutions.

Advantages of DeFi at the protocol level:

* Increased security at the application level - Verus DeFi is not implemented by having many smart contract authors creating smart contracts on top of the protocol, so there can be no exploits by searching for unintended "cracks" in the seams between contracts.

* Increased security at the protocol level - Verus DeFi is implemented in the protocol as part of the consensus, following the fundamental systems design principle which says that the most important security layers should be located in the system/protocol itself.

## Transactions Solved Simultaneously

The Verus protocol solves all transactions ``simultaneously`` within a block (as opposed to serially, in order, as is done on Ethereum and all other systems which use the virtual machine model). This has important implications for security, fairness, and efficiency:

* Elimination of front-running.

* Enhancing system-wide liquidity, thus reducing slippage, as conversions going to and from any given currency within the same block are offset against each other.

* Providing all users converting to and from a currency within the same block the same fair price with no spread.



