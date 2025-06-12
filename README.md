# CBD is the THC companion

CBD stands for Continuous Build & Deployment.

Check out [THC](https://github.com/social-dist0rtion-protocol/thc).

## GitHub Actions Setup for THC (Treasure Hunt Code) Deployment

This project requires specific GitHub secrets for deploying the Treasure Hunt Code (THC) application using GitHub Actions. The following secrets should be set up in your GitHub repository.

### Required Secrets

Add these secrets in your GitHub repository settings under **Settings > Secrets and variables > Actions > New repository secret**.

#### 1. `ETHEREUM_ENDPOINT`

- **Description**: Ethereum node endpoint URL for interacting with the Ethereum blockchain.
- **Example**: `https://mainnet.infura.io/v3/YOUR_INFURA_PROJECT_ID`

#### 2. `PRIVATE_KEY`

- **Description**: Private key for signing transactions. Make sure to store this securely.
- **Format**: A hexadecimal private key string, without the `0x` prefix.

#### 3. `VITE_RPC_NODE_URL`

- **Description**: Node URL used in the web build environment for connecting to the blockchain.
- **Example**: `https://mainnet.infura.io/v3/YOUR_INFURA_PROJECT_ID`

#### 4. `VITE_WALLET_CONNECT_PROJECT_ID`

- **Description**: Project ID for WalletConnect integration.
- **Example**: `YOUR_WALLET_CONNECT_PROJECT_ID`

#### 5. `DEPLOYER_SSH_KEY`

- **Description**: SSH private key for deploying the build to the target repository.
- **Format**: The private key content.
- **Generate**: `ssh-keygen -t ed25519 -C "deployer" -f github_actions_deploy_key`
- **IMPORTANT**:
  - After generating the key, add the public key (`github_actions_deploy_key.pub`) to the “Deploy Keys” section of the target repository (found in Settings > Deploy keys). This grants GitHub Actions permission to deploy changes to the target repository.
  - Enable **Allow write access**.

#### 6. `TARGET_REPO`

- **Description**: GitHub repository path (e.g., `username/repo-name`) where the built files will be deployed.
- **Example**: `my-username/target-repo`
