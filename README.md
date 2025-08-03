# AVA: DeFi Lending & Borrowing Platform

AVA is a decentralized finance (DeFi) application that enables users to lend and borrow ERC-20 tokens on the Ethereum blockchain. By leveraging smart contracts, AVA offers a transparent, secure, and efficient platform for decentralized lending and borrowing.

---

## 🚀 Features

- **Token Deposits**: Supply supported ERC-20 tokens to earn interest over time.
- **Collateralized Borrowing**: Borrow tokens by providing collateral, adhering to Loan-to-Value (LTV) ratios.
- **Dynamic Interest Rates**: Interest rates adjust based on pool utilization, promoting optimal liquidity.
- **Health Factor Monitoring**: Real-time assessment of loan safety to prevent liquidation.
- **Liquidation Mechanism**: Automatic liquidation of undercollateralized positions.
- **Token Faucet**: Access test tokens for development and testing.
- **Price Oracle Integration**: Uses Chainlink oracles for reliable price feeds.

---

## 🛠️ Technology Stack

### Smart Contracts
- **Solidity** – For writing secure Ethereum contracts
- **Hardhat** – For compiling, testing, and deploying contracts
- **OpenZeppelin** – Reusable smart contract standards

### Backend
- **Node.js** & **Express.js**
- **Web3.js** & **Ethers.js**

### Frontend
- **React.js**
- **Tailwind CSS**

### Testing & Security
- **Mocha** & **Chai** – For unit and integration testing
- **Slither** – Static analysis for smart contract vulnerabilities

---

## 📂 Project Structure

```bash
DEFI-Lending-Borrowing/
├── backend/               # Backend server and API
│   ├── contracts/         # Solidity smart contracts
│   ├── controllers/       # Request handlers
│   ├── router/            # Express routes
│   ├── scripts/           # Deployment & utilities
│   ├── test/              # Test files
│   └── index.js           # Entry point
├── frontend/              # React frontend
└── README.md              # Project documentation
```
## ⚙️ Installation & Setup
Prerequisites
Node.js v14+

Hardhat

MetaMask browser extension

```bash
# Clone the repo
git clone https://github.com/Nawasawank/DEFI-Lending-Borrowing.git
cd DEFI-Lending-Borrowing

# Install dependencies
npm install

# Compile smart contracts
npx hardhat compile

# Run local blockchain
npx hardhat node

# Deploy contracts to local network
npx hardhat run scripts/deploy.js --network localhost

# Start the backend server
cd backend
npm install
npm run dev

# Start the frontend application
cd ../frontend
npm install
npm start

```

## 📦 Environment Configuration
🔹 Frontend (frontend/.env)
The frontend requires the following environment variables in frontend/.env:
```bash
PORT                                    # Port for the React development server (default: 3000)
REACT_APP_TOKEN_SYMBOL_MAP              # JSON map of token addresses to their symbols {"0x..":"WETH","0x..":"WBTC",...}
REACT_APP_BACKEND_URL                   # Backend API base URL
REACT_APP_TOKEN_ADDRESS                 # ERC-20 token contract addresses for WETH, WBTC, USDC, DAI, GHO
```
🔹 Backend (backend/.env)
The backend requires the following environment variables in backend/.env:
```bash
PORT=3001
PRICE_CONTRACT_ADDRESS=0x..
LENDING_POOL_ADDRESS=0x..
INTEREST_RATE_MODEL_ADDRESS=0x..
LIQUIDATION_ADDRESS=0x..
FAUCET_MAP='{
    "0x...": "0x...",
}' # Token : Faucet

CMC_API_KEY # Coin Market Cap API Key
PROVIDER_URL=http://127.0.0.1:7545
```

Visit the app: http://localhost:3000

## 🔐 Security Measures
- **Access Control** – Uses onlyOwner, onlyFaucet to restrict sensitive functions.
- **Reentrancy Guards** – Prevents reentrancy attacks via OpenZeppelin’s ReentrancyGuard.
- **Input Validation** – Validates all user inputs before processing.
- **Fallback Logic** – PriceOracle handles stale or invalid Chainlink data with fallback pricing.

## 🧪 Testing
- **Unit Tests** – Validate individual contract logic in isolation (/test directory).
- **Integration Tests** – Simulate full workflows such as deposit → borrow → repay → withdraw.

To run all tests:
```bash
npx hardhat test
```
video: https://www.youtube.com/watch?v=rKbrAa2_9g8
