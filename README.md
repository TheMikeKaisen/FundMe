
---

# **FundMe Smart Contract on zkSync Sepolia Testnet**  

This repository contains the **FundMe smart contract**, a crowdfunding solution built with **Solidity** and deployed on the **zkSync Sepolia Testnet**. The contract uses **Chainlink Price Feeds** to ensure contributions meet a minimum USD value and leverages zkSync’s Layer 2 solution for scalability and reduced transaction costs.  

---

## **Features**  
- **ETH/USD Conversion**: Real-time ETH-to-USD conversion using Chainlink Price Feeds.  
- **Gas Optimization**: Uses `immutable` and `constant` keywords for efficient gas usage.  
- **Custom Errors**: Implements `NotOwner` custom error for reduced gas consumption.  
- **Secure Withdrawals**: Ensures only the contract owner can withdraw funds, with all funders’ balances reset securely.  
- **Fallback and Receive Functions**: Handles unexpected ETH transfers effectively.  
- **Modularity**: A reusable `PriceConverter` library simplifies the ETH-to-USD conversion logic.

---

## **Technologies Used**  
- **Solidity (v0.8.18)**  
- **Chainlink Price Feeds**  
- **zkSync Layer 2 (Sepolia Testnet)**  
- **Remix IDE**  

---

## **Setup Instructions**

### Prerequisites  
- Install [MetaMask](https://metamask.io/) for interacting with zkSync Sepolia Testnet.  
- Add the zkSync Sepolia Testnet network to MetaMask:
  - **Network Name**: ZKsync Sepolia Testnet  
  - **RPC URL**: `https://sepolia.era.zksync.dev`  
  - **Chain ID**: `300`  
  - **Currency Symbol**: ETH  
  - **Block Explorer URL**: `https://sepolia.explorer.zksync.io`  

### Clone the Repository  
```bash
git clone https://github.com/yourusername/fundme-zksync-sepolia.git
cd fundme-zksync-sepolia
```

### Deploying the Contract  

1. **Compile the Contract**  
   Use Remix IDE or Hardhat to compile the smart contract. Ensure the Solidity version is set to `^0.8.18`.  

2. **Deploy Using Remix**  
   - Open the FundMe contract in Remix.  
   - Select the zkSync Sepolia plugin for deployment.  
   - Deploy the contract to zkSync Sepolia Testnet.  

3. **Deploy Using Hardhat (Optional)**  
   Follow the Hardhat configuration steps in the `hardhat.config.js` file for zkSync deployment.  

---

## **Files in the Repository**

### 1. **Contracts**  
- **FundMe.sol**: Main contract handling crowdfunding, funding logic, and withdrawals.  
- **PriceConverter.sol**: Library for ETH-to-USD conversion using Chainlink Price Feeds.  

### 2. **Scripts**  
- **deploy.js**: Script for deploying the contract using Hardhat (if applicable).  

---

## **How It Works**  

1. **Funding**  
   - Users send ETH to the contract using the `fund()` function.  
   - The `PriceConverter` library ensures the ETH amount meets the minimum USD threshold (set to `$5`).  

2. **Withdrawal**  
   - Only the owner (contract deployer) can withdraw the total funds.  
   - Funders’ balances are reset after withdrawal to avoid double spending.  

3. **Fallback and Receive**  
   - Handles direct ETH transfers to the contract address by automatically calling the `fund()` function.  

---

## **Key Learnings**  
- Deploying smart contracts on zkSync Layer 2 networks.  
- Efficient use of Chainlink oracles for real-time data feeds.  
- Implementing modular and gas-optimized Solidity code.  
- Handling ETH transfers securely with fallback and receive functions.  

---

## **zkSync Sepolia Testnet Details**  
- **RPC URL**: `https://sepolia.era.zksync.dev`  
- **Chain ID**: `300`  
- **Explorer**: [zkSync Sepolia Explorer](https://sepolia.explorer.zksync.io)  

---

## **Contributing**  
Feel free to open issues or submit pull requests to enhance the contract!  

---

## **License**  
This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.  

---

## **Contact**  
Connect with me on [LinkedIn](https://www.linkedin.com/in/your-linkedin-profile) or open an issue if you have any questions or feedback!  

---

You can replace placeholders like `yourusername` and `your-linkedin-profile` with your actual GitHub username and LinkedIn profile link. Let me know if you’d like to customize anything further!
