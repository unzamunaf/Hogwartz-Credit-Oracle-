🏰 Hogwarts Credit Oracle - Complete Setup Guide
📋 Project Overview
A decentralized credit scoring system built on Ethereum that allows users to mint House Badges, build credit scores through on-chain activities, and access loan eligibility based on their wizard ranking.

🛠️ Prerequisites
Required Software
MetaMask browser extension

Node.js (v16 or higher) - for local development

Git - for version control

Modern web browser (Chrome, Firefox, Brave)

Required Accounts
MetaMask Wallet with Sepolia ETH

Alchemy/Infura Account (for Sepolia RPC)

📁 Project Structure
text
hogwarts-credit-oracle/
├── contracts/                 # Smart contracts
│   ├── HouseBadgeNFT.sol     # NFT badge contract
│   ├── HogwartsCreditOracle.sol # Credit scoring contract
│   └── WizardToken.sol       # Utility token contract
├── frontend/                  # Web interface
│   ├── index.html            # Main HTML file
│   ├── style.css             # Styling
│   └── app.js                # Main JavaScript application
└── README.md                 # This file
🚀 Quick Start Guide
Step 1: Get Test ETH
Add Sepolia Network to MetaMask:

Network Name: Sepolia

RPC URL: https://sepolia.infura.io/v3/YOUR_PROJECT_ID

Chain ID: 11155111

Currency Symbol: ETH

Get Sepolia ETH:

Visit Alchemy Sepolia Faucet

Connect your wallet and request 0.5 Sepolia ETH

Step 2: Deploy Smart Contracts
Option A: Using Remix IDE (Recommended)
Go to Remix IDE

Create new files:

HouseBadgeNFT.sol

WizardToken.sol

HogwartsCreditOracle.sol

Copy and paste the contract code (provided separately)

Compile each contract:

Go to "Solidity Compiler" tab

Select compiler version 0.8.19+

Click "Compile"

Deploy in order:

First: Deploy WizardToken (no parameters)

Second: Deploy HouseBadgeNFT (no parameters)

Third: Deploy HogwartsCreditOracle (use NFT and Token addresses as parameters)

Save contract addresses for frontend configuration

Option B: Using Hardhat (Advanced)
bash
# Clone project
git clone <repository-url>
cd hogwarts-credit-oracle

# Install dependencies
npm install

# Configure environment
cp .env.example .env
# Add your private key and RPC URL to .env

# Deploy contracts
npx hardhat run scripts/deploy.js --network sepolia
Step 3: Set Up Frontend
Option A: Local Development
Create project folder:

bash
mkdir hogwarts-dapp
cd hogwarts-dapp
Create files:

index.html - Main HTML structure

style.css - Styling

app.js - Application logic

Update contract addresses in app.js:

javascript
this.contractAddresses = {
    oracle: 'YOUR_ORACLE_ADDRESS',
    nft: 'YOUR_NFT_ADDRESS', 
    token: 'YOUR_TOKEN_ADDRESS'
};
Run locally:

bash
# Using Python
python -m http.server 8080

# Using Node.js
npx http-server

# Using Live Server (VS Code extension)
# Right-click index.html → "Open with Live Server"
Option B: Host on GitHub Pages
Create GitHub repository

Upload all frontend files

Go to repository Settings → Pages

Select branch and folder → Save

Access via: https://username.github.io/repository-name

🎮 How to Use the dApp
1. Connect Wallet
Click "Connect Wizard Wallet"

Approve connection in MetaMask

Ensure you're on Sepolia network

2. Mint House Badge
Click "Mint House Badge"

Confirm transaction in MetaMask

This automatically initializes your credit profile

3. Build Credit Score
Record Loan Repayment (+5 points)

Record Successful Trade (+2 points)

Maintain Activity Streak (bonus points)

4. Check Loan Eligibility
View your updated credit score

See available loan amounts based on your wizard rank

Track your activity streak

5. Claim Rewards
Maintain 3+ day activity streak

Click "Claim Streak Reward" for 30 WZT tokens

🔧 Troubleshooting
Common Issues & Solutions
❌ "User not initialized" Error
Problem: User needs to be initialized in the Oracle contract
Solution:

Make sure you've minted a House Badge first

The badge minting should auto-initialize your profile

If still failing, use the "Force Initialize" button (if available)

❌ "Execution reverted" Error
Problem: Transaction is failing on-chain
Solutions:

Ensure you have enough Sepolia ETH for gas

Check that you're on the correct network (Sepolia)

Verify contract addresses are correct

❌ MetaMask Connection Issues
Solutions:

Refresh the page and try again

Check if MetaMask is unlocked

Ensure the site has connection permissions

Try disconnecting and reconnecting the wallet

❌ "Insufficient funds" Error
Problem: Not enough ETH for gas fees
Solution: Get more Sepolia ETH from a faucet

❌ Transactions Stuck/Pending
Solutions:

Check MetaMask activity tab

Try increasing gas limit

Wait a few minutes then retry

Debugging Steps
Check Browser Console (F12) for error messages

Verify Contract Addresses on Sepolia Etherscan

Test Contracts in Remix to isolate issues

Check Network - must be Sepolia testnet

Verify Gas Fees - ensure sufficient ETH balance

📊 Contract Addresses (Example)
text
Oracle: 0xB7E3A25f56D7cF4d34A5011c606fFA6aEED8b866
NFT: 0xD7845D9ABB6e3CDE2Af19f8cd39a48B42bC00A38  
Token: 0x2573B34247bA0908F13758d90D435036af6Fda39
Replace these with your actual deployed contract addresses

🎯 Features Checklist
✅ Core Functionality
Wallet connection

House Badge minting

User initialization

Credit score tracking

Activity recording

Loan eligibility

Streak rewards

✅ User Experience
Responsive design

Real-time updates

Transaction status

Error handling

Success notifications

🔐 Security Notes
This is a testnet demonstration only

Do not use real ETH or mainnet assets

Contract addresses should be verified on Etherscan

Never share your private keys or seed phrases

🚨 Emergency Recovery
If Something Breaks:
Clear browser cache and cookies

Reconnect MetaMask

Redeploy contracts if necessary

Use the provided emergency initialization script

Force Reset:
javascript
// In browser console
localStorage.clear();
window.location.reload();
📞 Support
Getting Help
Check this README first for solutions

Review error messages in browser console

Test contracts individually in Remix

Verify all steps were followed correctly

Common Success Path
Get Sepolia ETH ✅

Deploy contracts ✅

Update frontend addresses ✅

Connect wallet ✅

Mint badge ✅

Use all features ✅

🎉 Congratulations!
Once you complete all steps, you'll have a fully functional decentralized application where users can:

🏠 Mint unique House Badges

📊 Build on-chain credit scores

💰 Access loan eligibility

🎁 Earn token rewards

📈 Track financial activities

Remember: This is a demonstration on testnet. The concepts can be adapted for real-world applications with proper security and auditing.

Built with magic and smart contracts ✨