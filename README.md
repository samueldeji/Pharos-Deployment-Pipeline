Pharos Deployment Pipeline

A practical one-command deployment tool for **Pharos Network**.

What I'm Building
A full pipeline that takes Solidity source code, compiles it, verifies the bytecode on-chain, routes through SPN (Special Processing Networks), runs early compliance checks, and deploys in a single smooth flow.

 What the Tool Does
- Compiles Solidity contracts
- Verifies deployed bytecode matches source code
- Handles SPN routing for optimal processing
- Flags ZK-KYC/AML related calls early
- Provides clear console feedback
- Aims for one-command deployment

Current Status (Working Today)
The core connection to Pharos mainnet is already built and tested.

js
const { ethers } = require("ethers");

async function deployToPharos() {
  const provider = new ethers.JsonRpcProvider("https://rpc.pharos.xyz");
  
  const network = await provider.getNetwork();
  const block = await provider.getBlockNumber();
  
  console.log("✅ Connected to Pharos Mainnet");
  console.log("Chain ID:", network.chainId);
  console.log("Latest Block:", block);
  // Next steps: compile → bytecode verify → SPN deploy
}

deployToPharos();
