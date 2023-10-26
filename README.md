# CustomERC20
A simple erc20 token that is tradeable, transferable and also has an orcale to give it certain prices.



Creating an ERC-20 token with an oracle to fetch prices involves multiple components. Below is a simplified example in Solidity to give you an idea of how it could work. This example assumes you're using the Chainlink oracle to fetch prices. Remember that you'll need to import the Chainlink contracts and interfaces to compile this code.

First, install the Chainlink contracts in your local environment if you haven't already:
```bash
npm install @chainlink/contracts
```

### Components:

1. **MyERC20Token**: This is a basic ERC-20 token using OpenZeppelin's ERC20 contract. It mints 10,000 tokens to the deployer upon creation.
  
2. **AggregatorV3Interface**: This is Chainlink's interface to interact with their price feed oracle.

3. **getLatestPrice**: Fetches the latest price from the Chainlink oracle.

4. **transferWithPriceCheck**: A new transfer function that checks the latest price before executing the transfer. For example, if the fetched price is greater than $3000, it transfers 5% fewer tokens.

### Important Notes:

- Make sure to replace the price feed address with the correct address for your network.
- This is a basic example; in a production environment, you should handle security considerations, error checks, and more complex business logic.
- You'll need Chainlink tokens to pay for the oracle requests when deploying to a testnet or mainnet.
- Always audit your code before deploying it to a mainnet.

To deploy and interact with this contract, you would use a framework like Truffle or Hardhat, along with a wallet that can sign transactions for the Ethereum network.
