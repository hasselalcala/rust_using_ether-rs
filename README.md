# How to create a connection using ganache and Ether-rs

## transaction.rs

In this project I create a ganache instance using a mnemonic, query the balance of our account, create a transaction to transfer 1000 wei to "another_address" and wait for receipt.

To access the wallet created by ganache, first get the private keys and then converthem to the `LocalWallet` instance. After that, to interact with the Ethereum node or network, we need to create a client which connects to the ganache endpoint.

When our client is connected to an Ethereum network, we can query the balance of any address in our wallet (using and address in hex string format and convert this string to a `address` type). We will find out that we have got 100 ETH in our address (This is added by Ganache automatically).

Now, we can create a transaction to transfer some ethereum token to another address. 


## deploy.rs

I create a ganache instance using a mnemonic, also use some solidity smart contract to compile and print compiled project information. To deploy the contract is necessary to create a transaction to get the ABI and contract byte.

First, we provide the directory that holds the solidity smart contracts, and create and configure a `ProjectBuilder`. Now we can compile our project and get all the artifacts from the compiled project.

To deploy the contract, we need to find the compiled contract by name using the `find` method, get the ABI and bytecode of this contract, create a `SignerMiddleware` for signing the contract deployment transaction, set the chain ID manually (if we use the default value might not be consistent with the Chain ID that our network is using), create a `ContractFactory` and deploy the contract. 

