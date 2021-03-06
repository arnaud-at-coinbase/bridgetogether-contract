# BridgeTogether

Project built during Coinbase's SmartContract Hack Days 2022. The goal is to
build a smart contract and website to aggregate on-chain deposit and make
bridging less expensive.

# Installing

## Dependencies
You'll need to install `npm`. Once done, run `npm install`.

## Run a Hardhat node
You can do this with `npx hardhat node`

## Install CB Wallet extension (dev edition!)
See [this slide deck](https://docs.google.com/presentation/d/1qbp6mZQRWM1mojehQbD7zex7-RINRGUJWRiNsAWvIww/edit#slide=id.g1110cabac13_0_131)

# Contents and tasks

The project comes with a sample contract, a test for that contract, a sample
script that deploys that contract, and an example of a task implementation,
which simply lists the available accounts. It also comes with a variety of
other tools, preconfigured to work with the project code.

Try running some of the following tasks:

```shell
npx hardhat accounts
npx hardhat compile
npx hardhat clean
npx hardhat test
npx hardhat node
npx hardhat help
REPORT_GAS=true npx hardhat test
npx hardhat coverage
npx hardhat run scripts/deploy.js
node scripts/deploy.js
npx eslint '**/*.js'
npx eslint '**/*.js' --fix
npx prettier '**/*.{json,sol,md}' --check
npx prettier '**/*.{json,sol,md}' --write
npx solhint 'contracts/**/*.sol'
npx solhint 'contracts/**/*.sol' --fix
```

# Etherscan verification

To try out Etherscan verification, you first need to deploy a contract to an Ethereum network that's supported by Etherscan, such as Ropsten.

In this project, copy the .env.example file to a file named .env, and then edit it to fill in the details. Enter your Etherscan API key, your Ropsten node URL (eg from Alchemy), and the private key of the account which will send the deployment transaction. With a valid .env file in place, first deploy your contract:

```shell
hardhat run --network ropsten scripts/deploy.js
```

Then, copy the deployment address and paste it in to replace `DEPLOYED_CONTRACT_ADDRESS` in this command:

```shell
npx hardhat verify --network ropsten DEPLOYED_CONTRACT_ADDRESS "Hello, Hardhat!"
```
