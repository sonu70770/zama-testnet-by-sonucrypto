# zama-testnet-by-sonucrypto

#  Guide  GitHub Commits **Zama Developer Program**

---

##  Step-by-Step Instructions

###  Create a New Repository

- Visit: https://github.com/new  
- Repository Name: `zama-commit-test` (or any name)  
- Set to **Public**  
- Tick "Add a README file"  
- Click **Create repository**

---

###  Open Codespace

- After repo creation, click the green `<> Code` button  
- Select: **Open with Codespaces → + New codespace**  
- Wait for Codespace to load (~20 seconds)

---

###  Open Terminal in Codespace

---

###  Run the Following Commands

Paste the following one-by-one or all together in the terminal:

```bash
echo "Commit 2 line" >> README.md
git add README.md
git commit -m "Commit 2"

echo "Commit 3 line" >> README.md
git add README.md
git commit -m "Commit 3"

echo "Commit 4 line" >> README.md
git add README.md
git commit -m "Commit 4"

echo "Commit 5 line" >> README.md
git add README.md
git commit -m "Commit 5"

echo "Commit 6 line" >> README.md
git add README.md
git commit -m "Commit 6"

echo "Commit 7 line" >> README.md
git add README.md
git commit -m "Commit 7"

echo "Commit 8 line" >> README.md
git add README.md
git commit -m "Commit 8"

echo "Commit 9 line" >> README.md
git add README.md
git commit -m "Commit 9"

echo "Commit 10 line" >> README.md
git add README.md
git commit -m "Commit 10"
```
```bash
git push
```

---

 #   “Write Your First Confidential Smart Contract”

###  STEP 1: Open Template in Codespace
1. Go to  https://github.com/zama-ai/fhevm-hardhat-template
2. Click the green Code button
3. Select → Open with Codespaces → + New codespace
4. Wait for Codespace to fully load and initialize

---

###  Step 2: Clean and Recreate Contracts Folder
```bash

rm -rf contracts/*
mkdir contracts
touch contracts/Calculator.sol
```
---

###  Step 3: Add Calculator Contract

1. Open ```contracts``` 
2. Right Click 
3. Add file
4. Create ```/Calculator.sol``` and paste this code:
```bash

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract Calculator {
    function encryptedAdd(uint32 a, uint32 b) public pure returns (uint32) {
        return a + b;
    }
}
```

---

###  Step 4: Install Required Packages
```bash
npm install
npm install @fhenixprotocol/contracts --save
```

###  Step 5: Compile the Contract
```bash
npx hardhat compile
```

Output should show:  ```Compiled 1 Solidity file successfully```

  ---

#  Level 3: “Submit Contract Address”

---

###  Step 1: Create scripts Folder

```bash
mkdir scripts
````

---

###  Step 2: Create Deploy Script File

```bash
touch scripts/deploy.js
```

• Then in Codespace (left sidebar):

→ Open `scripts/deploy.js`
→ Paste the following code:

```javascript
const hre = require("hardhat");

async function main() {
  const Calculator = await hre.ethers.getContractFactory("Calculator");
  const calculator = await Calculator.deploy();
  await calculator.waitForDeployment();

  console.log("Calculator deployed to:", await calculator.getAddress());
}

main().catch((error) => {
  console.error(error);
  process.exitCode = 1;
});
```

---

###  Step 3: Deploy the Contract

Run this in terminal:

```bash
npx hardhat run scripts/deploy.js
```

Expected output:

```bash
Calculator deployed to: 0xAbC...123
```

That address is your deployed smart contract address.

---

###  Step 4: Claim Level 3
