# Developer Guide

This section walks through tokenizing an AI agent using ASSETRA’s SDK and smart contract templates. We will demonstrate deploying a sample agent, registering metadata, and minting tokens.

1. **Setup environment**  
   ```bash
   npm install assetra-sdk ethers
   ```

2. **Initialize SDK**  
   ```javascript
   import { AssetraSDK } from 'assetra-sdk';
   const sdk = new AssetraSDK({ network: 'polygon' });
   ```

3. **Register AI Agent**  
   ```javascript
   const metadata = {
     name: 'Predictive Model v1',
     description: 'Time-series forecasting agent',
     repository: 'https://github.com/your-org/model-v1'
   };
   const receipt = await sdk.registerAgent(metadata);
   console.log('Agent registered:', receipt.agentId);
   ```

4. **Mint Token**  
   ```python
   from web3 import Web3
   w3 = Web3(Web3.HTTPProvider('https://rpc.polygon.io'));
   contract = w3.eth.contract(address=agentTokenAddress, abi=abi);
   tx = contract.functions.mintToken(userAddress, 1).transact({'from': deployer});
   ```

5. **Distribute Revenue**  
   ```solidity
   function distributeRevenue(uint256 _agentId) external {
     // revenue splitting logic
   }
   ```

Use this guide as a template to integrate your own AI workflows. For advanced use, refer to the API reference and governance module documentation.