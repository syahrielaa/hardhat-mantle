# hardhat-mantle

Hardhat plugin for mantle Developers.

## Features

mantleScan Contract Verification

## Prerequisites

Before the installation steps you need to have your hardhat project initialized using the command

```bash
npx hardhat init
```

Make sure to have dependencies installed!

## Installation

Use the following command to install

```bash
npm i hardhat-mantle --save-dev
```

Import the plugin in your `hardhat.config.js`:

```js
require("hardhat-mantle");
```

Or if you are using TypeScript, in your `hardhat.config.ts`:

```ts
import "hardhat-mantle";
```

Remove / Comment the import for `@nomicfoundation/hardhat-toolbox`

Add the following configuration to the `config` object in `hardhat.config.js`.

```js
networks: {
        mantleGoerli: {
            // can be replaced with the RPC url of your choice.
            url: "https://goerli-rollup.mantle.io/rpc",
            accounts: [
                "<YOUR_PRIVATE_KEY>"
            ],
        },
        mantleOne: {
            url: "https://rpc.mantle.xyz	",
            accounts: [
                "<YOUR_PRIVATE_KEY>"
            ],
        }
    },
    etherscan: {
        apiKey: {
            mantleGoerli: "<OPTIMISMSCAN_API_KEY>",
            mantleOne: "<OPTIMISMSCAN_API_KEY>"
        },
    },
```

Verify your contracts using the following command (Make sure your contracts are compiled before verification)

mantle Goerli Testnet

```bash
npx hardhat verify <CONTRACT_ADDRESS> <CONSTRUCTOR_ARGS> --network mantleGoerli
```

mantle Mainnet

```bash
npx hardhat verify <CONTRACT_ADDRESS> <CONSTRUCTOR_ARGS> --network mantleOne
```
