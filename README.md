# Decentralized Blockchain & Cryptocurrency Simulation

A complete, full-stack, decentralized blockchain network implementation written in Python. This project demonstrates the core technical mechanics of a blockchain—including cryptographic identity, decentralized consensus, cryptographic verification, a transactional engine, peer-to-peer networking, and an active frontend dashboard.

## Features & Implementation Details

* **Cryptographic Security & Verification**: Implements asymmetric cryptography (RSA 1024) to securely generate node wallets containing private/public key pairs. Transactions are cryptographically signed using `PKCS1_v1_5` and verified across the network to enforce security and digital ownership.
* **Proof-of-Work (PoWork) Consensus**: Implements a computational mining puzzle requiring block hashes to start with specified leading zeros. This regulates block generation rates and controls coin issuance via automated mining rewards.
* **P2P Network Node Synchronization**: Built with a Flask-RESTful API framework that enables decentralized nodes to broadcast new transactions and blocks dynamically over HTTP.
* **Conflict Resolution Protocol**: Features an autonomous longest-chain rule consensus mechanism. Nodes automatically request peer chains, evaluate validity, and resolve structural state splits to synchronize the universal system ledger.
* **State Persistence & Error Management**: Features robust file I/O operations using structural JSON formats to continuously save and reload local block ledgers, network peer endpoints, and wallet credentials securely.

## Built With

* **Backend**: Python 3, Flask (REST API Routing), Flask-CORS
* **Cryptography**: PyCryptodome (RSA, PKCS1_v1_5 signing, SHA256 hashing)
* **Frontend Interface**: Single Page Web App (Vue.js / Axios client communications, HTML5, Bootstrap)

---

## Architecture Diagram


---

## Getting Started & Setup Procedures

Follow these steps to initialize local peer-to-peer blockchain nodes.

### 1. Prerequisites
Ensure you have Python 3.x installed on your machine. Install the required dependencies using pip:
```bash
pip install Flask flask-cors pycryptodome requests
```
*   **Launch Node Instance 1 (Peer Node on Port 5000):**
```bash
python node.py -p 5000
```
*   **Launch Node Instance 2 (Peer Node on Port 5001):**
```bash
    python node.py -p 5001
```

### Step 3: Interacting with the Network
1.  **Open the Dashboard**: Navigate to `http://localhost:5000` in your web browser to view Node 1's graphical user interface. Open `http://localhost:5001` in a separate tab to view Node 2.
2.  **Initialize Wallets**: On both nodes, click **"Create New Wallet"** or **"Load Wallet"**. This initializes your cryptographic keys; without them, the node cannot create valid transactions or receive block rewards.
3.  **Establish Peer Topology**: Go to the Network Configuration tab on Node 1 (`http://localhost:5000/network`). Input the network string for Node 2 (`localhost:5001`) and register it. The nodes are now linked.
4.  **Send & Mine Currency**: Create a transaction from Node 1 to Node 2's public key. The transaction will sit in the *Open Transactions* mempool. Click **"Mine Block"** on either node to solve the cryptographic proof-of-work puzzle and write the transactions permanently into the global blockchain ledger.

---

## 5. Repository Structure Blueprint

*   `node.py`: The application's main entry point. Initializes the Flask API routing tables, manages incoming peer network webhook requests, and orchestrates client UI serving.
*   `blockchain.py`: Main domain logic controller. Manages state changes, builds valid block containers, tallies historical account balances, and performs peer chain synchronization.
*   `wallet.py`: Dedicated cryptographic utility wrapper managing RSA key allocations, transaction string serialization, and signing/verification operations.
*   `block.py` & `transaction.py`: Pure Object-Oriented models defining the structural data fields required for valid blocks and network trades [cite: yanivbohbot/blockchain-in--python-/BLOCKCHAIN-IN--PYTHON--3f40b8c5f68d89ff3909cdcf72ef5fef9ce766ae/BlockChain in Python/block.py, yanivbohbot/blockchain-in--python-/BLOCKCHAIN-IN--PYTHON--3f40b8c5f68d89ff3909cdcf72ef5fef9ce766ae/BlockChain in Python/transaction.py].
*   `utility/verification.py`: Validation module containing static evaluation functions that review proof-of-work compliance, transaction structure validity, and entire chain structural health.
*   `utility/hash_util.py` & `printable.py`: Low-level helpers providing uniform SHA-256 string hashing algorithms and pretty-printing properties for debug environments [cite: yanivbohbot/blockchain-in--python-/BLOCKCHAIN-IN--PYTHON--3f40b8c5f68d89ff3909cdcf72ef5fef9ce766ae/BlockChain in Python/utility/hash_util.py, yanivbohbot/blockchain-in--python-/BLOCKCHAIN-IN--PYTHON--3f40b8c5f68d89ff3909cdcf72ef5fef9ce766ae/BlockChain in Python/utility/printable.py].

--
