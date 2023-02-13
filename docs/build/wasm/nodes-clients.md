---
sidebar_position: 3
---

# Smart Contract Development Nodes

## Local Development Nodes

### Swanky Node

Swanky Node is a local development node tracking the Shiden network.

Swanky Node is the best choice for developing and testing smart contracts in a local environment, prior to deployment on Shiden or Astar mainnets.

Features:

- Consensus: `instant-seal` and `manual-seal`
- dApp staking enabled
- Chain Extensions

For more information, the Github repository can be [here](https://github.com/AstarNetwork/swanky-node).

### Substrate Contract Node

The Substrate contract node targets Substrate master, and is the best choice for testing the very latest (or unstable) features of ink! and/or `pallet-contracts`.

Features:

- Targets the latest Substrate master
- Consensus: `instant-seal`

For more information, the Github repository can be found [here](https://github.com/paritytech/substrate-contracts-node).

## Testnet Node: Shibuya

The Shibuya testnet chain specifications nearly mirror those on Shiden & Astar mainnets, so provides an ideal environment for developers to test their smart contracts and dApps, prior to launching them in a production environment.

Shibuya's `pallet-contracts` has `unstable-feature` enabled, so you are able to use ink! features flagged unstable in `pallet-contracts`.

For all the latest information about Shibuya or obtain tokens from the faucet, consult the official documentation, or visit the [Test Tokens](../environment/faucet.md) page in the previous section.

## Mainnet Node: Shiden

Wasm contracts are live on Shiden. You can interact with them in the same way as you would on Shibuya.

## Mainnet Node: Astar

At the moment, Wasm smart contracts are not available on Astar. They should go live during 2023 Q1.
