# LTC MWEB Pay 🚀

> **Accept Litecoin with full privacy via MWEB. No processing fees. No intermediaries.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Litecoin](https://img.shields.io/badge/Crypto-Litecoin-345D9D.svg)](https://litecoin.org/)
[![MWEB](https://img.shields.io/badge/Feature-MWEB-8A2BE2.svg)](https://litecoin.com/mweb)

## What is it?

**LTC MWEB Pay** is a lightweight, self-hosted payment gateway for accepting Litecoin using MimbleWimble Extension Blocks (MWEB) technology.

Unlike traditional processors, we do not hold your funds or require KYC. Payments go directly from the buyer to your wallet. We simply provide the tool to generate invoices and monitor payment confirmation on the blockchain.

### Why is it cool?
*   🔒 **Privacy by Default:** MWEB usage hides transaction amounts and participants.
*   💸 **0% Service Fees:** You only pay the Litecoin network fee (which is negligible).
*   🏠 **Full Control:** Runs on your server. Your keys, your coins.
*   ⚡ **Simplicity:** Up and running in 15 minutes via Docker.
*   🐍 **Open Source:** Built with Python (FastAPI). Easy to audit and extend.

## Architecture

The project consists of two main components running in Docker:
1.  **Litecoin Node:** A full node for network validation and MWEB interaction.
2.  **Payment Processor (API):** A lightweight Python service that communicates with the node, creates invoices, and listens for payment events.

## Quick Start (For Merchants)

You will need a Linux server (Ubuntu/Debian) with Docker & Docker Compose installed.

### 1. Clone the repository

```bash
git clone https://github.com/vic-che/ltc-mweb-pay.git
cd ltc-mweb-pay
```

### 2. Configure environment

Copy the example environment file and edit it:

```bash
cp .env.example .env
nano .env
```

In the `.env` file, specify the basic parameters (see Configuration section for details).

### 3. Run

```bash
docker-compose up -d
```

The first launch may take some time as the Litecoin node needs to synchronize the blockchain. You can monitor the status via logs:

```bash
docker-compose logs -f processor
```

## For Developers

If you want to contribute to the project or run it in development mode:

1.  Install Python dependencies:
    ```bash
    python -m venv venv
    source venv/bin/activate
    pip install -r requirements.txt
    ```
2.  Run a local node (or connect to an existing one).
3.  Start the API:
    ```bash
    uvicorn main:app --reload
    ```

## Documentation

Full documentation on API, store integration setup, and MWEB workflow explanation is located in the `/docs` folder (under development) or on our website [ltc-mweb-pay.com](http://ltc-mweb-pay.com).

## Roadmap

- [x] Project initialization and basic architecture
- [ ] Implementation of MWEB address generation via RPC
- [ ] Integration with FastAPI and creation of invoice endpoints
- [ ] Web interface for viewing payments
- [ ] Plugins for popular CMS (WooCommerce, PrestaShop)

## License

This project is distributed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Support

If you have questions or ideas, please create an Issue on GitHub. We are building a community focused on privacy and payment freedom.

---
*Made with ❤️ and Python.*
```
