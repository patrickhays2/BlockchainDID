# Blockchain DID Specification

## Summary

The Blockchain DID Specification aims to provide a simple, lightweight method of resolving wallet addresses, smart contracts, and NFTs, and other blockchain-related assets regardless of on which network or chain they are located.

## Status of This Document

This document is a draft and is in the process of being updated. The Blockchain DID method is primarily concerned with blockchains derived from and compatible with the Etheruem Blockchain, but will expand to other networks after sufficient development has progressed.

## Blockchain DID Method

The namestring that identifies this DID method is: `blockchain`. A DID that uses this method MUST begin with the prfiex `did:blockchain` and the string MUST be lowercased in accordance with [W3 DID Core Specifications](https://www.w3.org/TR/did-core). The Blockchain DID method is defined by the following ABNF:

```
blockchain-did = "did:blockchain:" identification-method
identification-method = eth ; Other chain types are in development.
eth = "eth:" chain-id ":" etheruem-address [ ":" token-id ]
chain-id = 1*DIGIT
ethereum-address = "0x" 40*HEXDIG
token-id 1*DIGIT
```

| Property | Value |
|:---|:---|
| `blockchain-did` | "did:blockchain:" `blockchain-network-method` |
| `blockchain-network-method` | `eth` (*other chain types are in development.*) |
| `eth` | "eth:" `eth-chain-id` ":" `eth-address` [ ":" `eth-token-id` ] [ ":" `eth-token-type` ]|
| `eth-chain-id` | 1*DIGIT |
| `eth-address` | "0x" 40*HEXGID |
| `eth-token-id` | 1*DIGIT |
| `eth-token-type` | "bep20" / "erc721" / erc1155 |

### Examples:

A valid Blockchain DID be:

- `did:blockchain:eth:1:0x1B6D345878Fc9531653F74D3630c32650677f42e` specifies the contract at address *0x1B6D345878Fc9531653F74D3630c32650677f42e* on the *Ethereum Blockchain*.
- `did:blockchain:eth:56:0x0f0B8B1B9F4ec7CCa8BB2792636cFE09c2488Eb9:584` specifies token number *584* minted by the contract at address *0x0f0B8B1B9F4ec7CCa8BB2792636cFE09c2488Eb9* on the *Binance Smart Chain*.
- `did:blockchain:eth:137:0xaDE6E3bac3424cc6893289540B22BDd2f168Aa91:176:erc721` specifies the *ERC-721* token number *176* minted by the contract at address *0xaDE6E3bac3424cc6893289540B22BDd2f168Aa91* on the *Polygon Blockchain*.

## CRUD

Blockchain DIDs and DID Documents can be created stored on an accessible resource or can be derived by the software platform dependent on the needs of the developer. Both the DID and its corresponding DID Document are registered or recorded as required.

Registry DIDs:
- did:blockchain:eth:1:0x0f0B8B1B9F4ec7CCa8BB2792636cFE09c2488Eb9
- did:blockchain:eth:56:0x0f0B8B1B9F4ec7CCa8BB2792636cFE09c2488Eb9
- did:blockchain:eth:137:0x0f0B8B1B9F4ec7CCa8BB2792636cFE09c2488Eb9

### Create

Blockchain DIDs and DID Documents can be created stored on an accessible resource or can be derived by the software platform dependent on the needs of the development team. Both the DID and its corresponding DID Document are registered or recorded as required.

### Resolve

`getDIDDocument()`

### Update

`alsoKnownAs()`
`addService()`

### Delete
