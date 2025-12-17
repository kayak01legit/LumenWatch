# LumenWatch

Built for Base

LumenWatch is a Base-oriented repository created to continuously observe key onchain signals such as chain identity, block progression, and account balances using official Coinbase tooling.

The repository is designed as a lightweight verification layer rather than a feature-heavy application.

## Intent

LumenWatch is used to:
- Validate Base Mainnet and Base Sepolia connectivity
- Confirm chainId accuracy (8453 / 84532)
- Exercise wallet onboarding via OnchainKit
- Perform deterministic, read-only onchain queries
- Cross-check results with Basescan explorers

## Supported Networks

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  
RPC: https://mainnet.base.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  
RPC: https://sepolia.base.org  

## Application Overview

Primary file: app/lumenWatch.ts

At runtime, the application:
- Boots an OnchainKitProvider bound to the selected Base chain
- Displays wallet connection UI
- Uses Viem to query:
  - RPC-reported chainId
  - latest block number
  - native ETH balance for a supplied address
- Keeps Basescan links visible for manual verification

## Project Structure

app/  
- lumenWatch.ts  
  React entry component combining OnchainKit wallet UX with Base JSON-RPC reads.

Typical supporting files:
- package.json
- tsconfig.json
- index.html / main.tsx
- .env

## Libraries and Tooling

OnchainKit  
https://github.com/coinbase/onchainkit  

Viem  
EVM client for Base JSON-RPC reads  

## Installation and Execution

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies using your preferred package manager and run with a standard React/Vite or Next.js development server.

Optional environment variables:
- VITE_BASE_RPC_URL
- VITE_BASE_SEPOLIA_RPC_URL

## License

MIT License

## Author

GitHub: https://github.com/kayak01legit 

Public contact (email): kayak01legit@icloud.com

Public contact (X): https://x.com/ystinovapolinka  

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract #1 address:  
0x63caf4357667c42d2d10f4629c8c910cc1903b0f 

Deployment and verification:
- https://sepolia.basescan.org/address/0x63caf4357667c42d2d10f4629c8c910cc1903b0f 
- https://sepolia.basescan.org/0x63caf4357667c42d2d10f4629c8c910cc1903b0f/0#code  

Contract #2 address:  
0x1187f51d68add454cd2c56d79e483288435310be

Deployment and verification:
- https://sepolia.basescan.org/address/0x1187f51d68add454cd2c56d79e483288435310be
- https://sepolia.basescan.org/0x1187f51d68add454cd2c56d79e483288435310be/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
