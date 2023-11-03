---
namespace-identifier: ergo-caip2
title: Ergo - Blockchain ID Specification
author: ["Mark Glasgow (@glasgowm148)"]
status: Draft
type: Standard
created: 2023-11-03
requires: "CAIP-2"
---

# CAIP-2

*For context, see the [CAIP-2](https://github.com/ChainAgnostic/CAIPs/blob/master/CAIPs/caip-2.md) specification.*
<!-- Contributing Guide: https://github.com/glasgowm148/namespaces/blob/main/CONTRIBUTING.md --->

Ergo identifies its networks using a combination of network type and port number, unlike EVM chains that may use a different network ID. This distinction is crucial for developers and systems interacting with Ergo, ensuring they are communicating with the correct network.

## Rationale

Implementing CAIP-2 within the Ergo namespace provides a standard approach to blockchain identification, ensuring interoperability and reducing the chance of cross-chain confusion.


## Semantics


The `namespace` "ergo" covers the Ergo blockchain network. The `reference` is a combination of the network type (mainnet, testnet) and the port number, which identifies a specific blockchain within the Ergo network.

Let's look at the prefix byte, which contains information about the network and address types:

Possible network types are:

* Mainnet - `0x00`
* Testnet - `0x10`

Address types are (semantics described below):

* `0x01` - Pay-to-PublicKey(P2PK) address
* `0x02` - Pay-to-Script-Hash(P2SH)
* `0x03` - Pay-to-Script(P2S)



## Syntax

The syntax for blockchain identification in Ergo is as follows:

```
chainId: namespace + ":" + reference
namespace: ergo
reference:   {network type} + {port number}
```

### Resolution Mechanics

Resolving a blockchain reference within the Ergo namespace can be performed through a request to an Ergo Explorer API, using the port number to specify the network:

Here's a sample request and response for validating a transaction against the Ergo blockchain using the Ergo node API:

Request:
```
GET api.ergoplatform.com/api/v1/transactions/{txId}
```

Response:
```
{
  "id": "txId",
  "inputs": [...],
  "outputs": [...],
  "size": 1234,
  "timestamp": 1634567890,
  "blockId": "blockId",
  "confirmations": 10,
  ...
}
```

To validate the results, you can check the response for the presence of the transaction ID, inputs, outputs, size, timestamp, block ID, and confirmations. These details confirm that the transaction exists on the Ergo blockchain and provide information about its inputs, outputs, size, timestamp, and block confirmation status.

To calculate checksums or perform additional validation steps, you may need to refer to the ErgoScript documentation, which provides detailed information about the scripting language used in Ergo transactions.

For more information on the Ergo Explorer API and how to interact with the Ergo blockchain, you can refer to the Ergo documentation's API section [Ergo Explorer API Documentation][Ergo Explorer API v1].


### Backwards Compatibility

No known issues regarding backward compatibility.

## Test Cases

- Ergo Mainnet: `ergo:mainnet:9053`
- Ergo Testnet: `ergo:testnet:9052`


## Additional Considerations

Future protocol upgrades in Ergo may require updates to this specification to ensure continued alignment with the CAIP-2 standard.

## References

- [Ergo Node API Reference](https://api.ergoplatform.com/api/v1/docs/)
- [Ergo Address Format](https://docs.ergoplatform.com/dev/wallet/address/address_types/)
- [Ergo Explorer](https://explorer.ergoplatform.com/en/)
- [CAIP-2 Specification](https://github.com/ChainAgnostic/CAIPs/blob/master/CAIPs/caip-2.md)
- [EIP-0012: dApp-Wallet Web Bridge](https://github.com/ergoplatform/eips/blob/720b188be84415eba0f3cffb0258354ea38eca6c/eip-0012.md) is a wrapper around a JSON-RPC protocol for dApp <-> Wallet interactions

[CAIP-2]: https://chainagnostic.org/CAIPs/caip-2
[Ergo Explorer API v1]: https://api.ergoplatform.com/api/v1/docs/
[Indexed Node API]: https://docs.ergoplatform.com/node/indexed-node/
[GraphQL]: https://docs.ergoplatform.com/dev/stack/explorer/graphql/


## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).




