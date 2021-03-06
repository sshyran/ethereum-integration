# POC 3

## Setup

- Install nodejs
- Install npm packages with `npm install`
- Install contracts with `truffle install`

## Query Engine

The POC 3 also uses a custom query engine for BigchainDB. The details about using and setting up the query engine can be found in [./query-engine/readme.md](./query-engine/readme.md).

The smart contract in POC 3 uses the query engine API for BigchainDB queries.

## Configure

- Get api key from [Infura.io](https://infura.io/)
- Generate keys and addresses with `npm run generate`
- Create .env file from .env-example

## Deploy contract

- Compile contracts with `truffle compile`
- Deploy contracts to either rinkeby or private Ethereum network `truffle migrate --network [rinkeby | development]`
- Update .env with new `BDBADAPTERADDRESS`

## Execute transfer

- Run transfer with `npm run start`

## Test

The test deploys the contract on the Rinkeby network, executes the oraclize query and listens to the events to track the progress of the query.

### To execute the test

- Modify the `test/TestParam.json` as per the requirement.
- Make sure the `from_address` mentioned in the `test/TestParam.json` is unlocked during the test execution and has sufficient funds. Since this account is going to be used for contract deployment and transaction execution.
- From command line/terminal run: `truffle test`.

## Additional Information - Running in private ethereum network

We requested the [Oraclize](https://www.oraclize.it) team to allow us to use [Stargate](https://docs.oraclize.it/#development-tools-future) (beta) for integration with private Ethereum network. They helped us with the credentials and setup instructions. From there, it was a breeze to setup Stargate and use it just like we use the Oraclize service for public Ethereum network.

Using `Stargate`, we were successful in running the POC end-to-end on our private ethereum network setup.

For more details on Stargate and how to use it, please directly [connect with the Oraclize team](mailto:info@oraclize.it).
