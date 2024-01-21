# NFT Project

## Overview

This repository contains the source code for the NFT Project.

## Getting Started

To clone the repository and its submodules, use the following command:

```bash
git clone --recurse-submodules -j8 https://github.com/panicd9/NFT-Project.git
```

## Technologies Used

- **Foundry:**
  - Anvil
  - Cast
  - Forge
- Remix IDE
- IPFS
- Ganache
- Go
- Solidity
- React
- Docker
- Postgres
- DBeaver
- Windows Subsystem for Linux (WSL)


## Project Components

The project is divided into the following components:

- Frontend: The user interface of the application, built using React.
- Backend: The server-side logic and functionality, implemented in Go.
- Smart Contract: EVM compatible smart contract written in Solidity.

## Notes

- Adding an address to the blacklist requires the user to sign a message in format ```Keccak256("Authorize-{unix_timestamp}-{address_to_blacklist}")``` to avoid calling endpoint without having deployer private key and to avoid MITM/replay attack. The signature is valid for 60 seconds.
- The frontend is attempting to render NFT images from IPFS, but since the images are likely hosted only on my IPFS node, it will render them from the local file system. Timeout for IPFS render is 2 seconds.
- Metamask's signature is Ethereum signature, go-ethereum's signature is ECDSA signature, so i used different package to verify signature on backend side to avoid manually creating Ethereum specific signature.
