# GeyikApp

This repository hosts the source for the revamped GeyikApp website and smart contracts.

The project uses **Node.js** for development, [Hardhat](https://hardhat.org/) for compiling Solidity contracts and running a local blockchain, and a lightweight frontend that can be deployed to IPFS or any other static host.

## Prerequisites

- [Node.js](https://nodejs.org/) 18 or later
- `npm` (ships with Node)

## Getting Started

1. **Install dependencies**

   ```bash
   npm install
   ```

2. **Compile smart contracts**

   ```bash
   npx hardhat compile
   ```

3. **Run the development server**

   ```bash
   npm run dev
   ```

   The frontend will be available at `http://localhost:3000` by default.

## Connecting Your Wallet

Open the site in a modern browser with MetaMask installed. Click the **Connect Wallet** button. MetaMask will prompt you to approve the connection. Once connected, your account address will appear in the header.

## Encryption

Sensitive data is encrypted client‑side using the user's wallet keys. When you sign in with MetaMask, your account's private key never leaves your browser. The app encrypts content before sending it to the server or IPFS, ensuring only the holder of the private key can decrypt it.

## AI Integration

The platform can utilize AI models through API endpoints. Requests are authenticated using your wallet address, and responses are encrypted before being stored. The AI modules can run either as external services or locally using Node.js processes.

## Deployment

### Frontend

To deploy the built site to IPFS:

```bash
npm run build
npx ipfs add -r dist
```

The command will output a hash that you can use to access the site from any IPFS gateway. Alternatively, you can upload the contents of `dist/` to any static host.

### Smart Contracts

Deploy contracts via Hardhat:

```bash
npx hardhat run scripts/deploy.js --network <network>
```

Replace `<network>` with a configured network in `hardhat.config.js` (e.g., `localhost`, `sepolia`, or `mainnet`).

## Contributing

1. Fork the repository and create a feature branch.
2. Commit your changes with clear messages.
3. Open a pull request describing your work.

## License

This project is provided under the MIT License. See [LICENSE](LICENSE) for more information.
