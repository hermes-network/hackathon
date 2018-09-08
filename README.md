# Hackathon
Hermes Network is a layer 2 execution market for Ethereum transactions. It comprises of two core pieces:
- [**Hermesjs**](https://github.com/hermes-network/hermesjs) A JS library for dapp developers, which creates signed executable transactions, and publishes them to the network.
- [**Hermes The Executor**](https://github.com/hermes-network/the-executor) A daemon, subscribing to a channel for incoming signed transactions, and submits them to the network, paying gas, and being refunded and rewarded.

## Why
Various projects aim to improve user experience by enabling recurring fee subscriptions, delegated conditional execution or sponsored gas. These second layer execution markets all share the need for a mechanism that submit signed user transactions to the network. We hope to implement a modular relayer that fulfills these requirements.

## MVP
In the Minimal Viable Product we aim to focus on [EIP-1077](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1077.md) style meta transactions, using Gnosis Safe as the implementation for the identity proxy.

## Flow
The following is a summary of different components of the network coming together:

- End user deploys an [identity proxy](https://github.com/hermes-network/safe-contracts) and puts ether in it. It's important to note that, this need be done only once by the user, and be used for different dapps, or dapps could handle this deployment process.
- There should be at least one executor node running.
- User can then interact with the [example dapp](https://github.com/hermes-network/demo) which internally is using [HermesJS](https://github.com/hermes-network/hermesjs) to create meta transactions and send them to the network.
- An executor picks up the transaction and submits it to the network, and being reimbursed for the gas.

## License
[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)
