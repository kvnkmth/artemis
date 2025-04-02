#### Artemis Core
Bare bones Artemis without the alloy evm dependancies
- Collectors
- Strategies
- Executors  

![](./assets/artemis.png)

[![CI status](https://github.com/paradigmxyz/reth/workflows/ci/badge.svg)][gh-ci]
[![Telegram Chat][tg-badge]][tg-url]

[gh-ci]: https://github.com/paradigmxyz/reth/actions/workflows/rust.yml
[tg-badge]: https://img.shields.io/badge/chat-telegram-blue

## What is Artemis?

Artemis is a framework for writing MEV bots in Rust. It's designed to be simple, modular, and fast. 

At its core, Artemis is architected as an event processing pipeline. The library is made up of three main components: 

1. *Collectors*: *Collectors* take in external events (such as pending txs, new blocks, marketplace orders, etc. ) and turn them into an internal *event* representation. 
2. *Strategies*: *Strategies* contain the core logic required for each MEV opportunity. They take in *events* as inputs, and compute whether any opportunities are available (for example, a strategy might listen to a stream of marketplace orders to see if there are any cross-exchange arbs). *Strategies* produce *actions*.
3. *Executors*: *Executors* process *actions*, and are responsible for executing them in different domains (for example, submitting txs, posting off-chain orders, etc.).

## Acknowledgements

- [subway](https://github.com/libevm/subway)
- [subway-rs](https://github.com/refcell/subway-rs)
- [cfmms-rs](https://github.com/0xKitsune/cfmms-rs)
- [rusty-sando](https://github.com/mouseless-eth/rusty-sando)
- [bundle-generator](https://github.com/Alcibiades-Capital/mev_bundle_generator/blob/master/Cargo.toml)
- [ethers-rs](https://github.com/gakonst/ethers-rs)
- [ethers-flashbots](https://github.com/onbjerg/ethers-flashbots)



[tg-url]: https://t.me/artemis_devs