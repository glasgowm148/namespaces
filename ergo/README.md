---
namespace-identifier: ergo
title: Ergo Blockchain
author: ["Mark Glasgow (@glasgowm148)"]
status: Draft
type: Informational
created: 2023-11-03
---

# Namespace for Ergo Blockchain

This document delineates the applicability of CAIP standards within the Ergo ecosystem, encompassing various projects issued as 'native tokens' standardised via [EIP-0004: Asset Standard][EIP-0004]

The Ergo blockchain is characterized by its distinctive design principles, advanced cryptographic features, and the ErgoScript smart contract language that employs an [extended UTXO (eUTXO)][UTXO vs Account: Understanding Ergo's Transaction Model] model.


## Governance


Ergo adopts an Improvement Proposal process ([EIPs][EIPs]) akin to other blockchain ecosystems, fostering a decentralized and democratic governance model through community-driven protocol amendments.

In Ergo, numerous network parameters can be modified via a decentralized voting mechanism among miners, encompassing computational costs, block size limits, and storage fees. This ensures long-term economic stability guided by miner consensus.

Miners have the provision to vote on altering specific protocol parameters. Soft-forking changes necessitate 90% miner support and can modify various Ergo aspects, excluding critical elements like the maximum supply. Refer to the [Miner Governance][Miner Governance] section for an in-depth understanding of voting mechanics, system constants, current network settings, parameters table, and the soft-forking mechanism.


## References
- [Ergo Website][]
- [Ergo GitHub][] - Repository for source code and improvement proposals.
- [ErgoScript Language][] - Official documentation for ErgoScript language.
- [Miner Governance][] - Detailed documentation on Ergo's miner governance mechanism.
- [EIPs][] - Ergo Improvement Proposals.
- [UTXO vs Account: Understanding Ergo's Transaction Model][]
- [EIP-0004][] - Standardization of token issuance on Ergo.

[Ergo Website]: https://ergoplatform.org/en/
[Ergo GitHub]: https://github.com/ergoplatform
[ErgoScript Language]: https://docs.ergoplatform.com/dev/scs/ergoscript/
[Miner Governance]: https://docs.ergoplatform.com/mining/governance/
[EIPs]: https://github.com/ergoplatform/eips
[UTXO vs Account: Understanding Ergo's Transaction Model]: https://docs.ergoplatform.com/dev/protocol/eutxo/accountveutxo/
[EIP-0004]: https://docs.ergoplatform.com/dev/tokens/standards/eip4/


## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
