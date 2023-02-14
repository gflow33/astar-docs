---
sidebar_position: 1
---

# Overview

This tutorial is suitable for developers with **intermediate** knowledge of ink! and basic understanding of Rust. Using the examples provided, you will build and deploy a PSP34 NFT using ink! with functions commonly seen in NFT projects.
- [PSP34 standard](https://github.com/w3f/PSPs/blob/master/PSPs/psp-34.md)

# Prerequisites

Previous experience compiling and deploying an ink! smart contract will be beneficial, such as from following the previous Flipper contract guide:

| Tutorial                                                                   | Difficulty                     |
|----------------------------------------------------------------------------|--------------------------------|
| [Your First Flipper Contract](../flipper-contract/flipper-contract.md)              | Basic ink! -  Basic Rust       | 
| [Implement Uniswap V2 core DEX](../dex/dex.md) | Advanced ink! - Basic Rust |         

In addition to:
- An already provisioned [ink! environment](/docs/build/environment/ink_environment.md).
- Basic knowledge of Rust. Visit [here for more information about Rust](https://www.rust-lang.org/learn).
- Prior knowledge of ERC721 will be beneficial, but is not necessary.

### What Version of Ink! Will I Need?
- [ink! 3.4.0 (latest)](https://github.com/paritytech/ink/tree/v3.4.0)   
- [Openbrush 2.3.0 (latest)](https://github.com/Supercolony-net/openbrush-contracts/tree/v2.3.0)

### What Topics Will Be Covered in This Guide?
- Full implementation of an NFT project in ink!
- How to use Openbrush wizard to create PSP34 smart contract.
- The file structure for a smart contract with an additional trait.
- Trait and generic implementation in separate files.
- Unit test for smart contract.
- Event handling.

# Summary
[I. OpenBrush wizard](./Wizard/wizard.md)   
[II. Override mint() method](./Override/override.md)   
[III Custom Trait for mint()](./CustomTrait/customtrait.md)   
[IV. PayableMint Trait definition](./PayableMintTrait/payableminttrait.md)   
[V. PayableMint Trait implementation](./PayableMintImpl/payablemintimpl.md)   
[VI. Events](./Events/events.md)   