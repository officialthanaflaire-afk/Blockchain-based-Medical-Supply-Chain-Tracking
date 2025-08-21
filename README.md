# 🌍 Blockchain-based Medical Supply Chain Tracking

Welcome to a decentralized solution for tracking medical supplies on the blockchain! This project leverages the Stacks blockchain and Clarity smart contracts to ensure transparency, traceability, and authenticity in the medical supply chain, addressing real-world issues like counterfeit drugs and supply chain inefficiencies.

## ✨ Features

🔍 **Track Provenance**: Trace medical supplies from manufacturer to end-user.  
🛡️ **Anti-Counterfeiting**: Verify the authenticity of medical products.  
📦 **Inventory Management**: Monitor stock levels across the supply chain.  
🚚 **Shipment Tracking**: Record and verify shipment details immutably.  
✅ **Regulatory Compliance**: Ensure adherence to standards with auditable records.  
🔐 **Permissioned Access**: Restrict sensitive operations to authorized parties.  
📊 **Analytics**: Generate supply chain reports for stakeholders.  

## 🛠 How It Works

This project uses 6 Clarity smart contracts to manage the medical supply chain process, ensuring transparency and security. Below is an overview of the system and its components.

### 📜 Smart Contracts

1. **ManufacturerRegistry**: Registers manufacturers and their authorized public keys.  
   - Functions: `register-manufacturer`, `update-manufacturer-details`, `get-manufacturer`.  
   - Purpose: Only registered manufacturers can create products.  

2. **ProductRegistry**: Manages product creation and metadata (e.g., drug name, batch number, expiry).  
   - Functions: `register-product`, `get-product-details`, `verify-product`.  
   - Purpose: Stores unique product IDs and prevents duplicates.  

3. **ShipmentContract**: Tracks shipments from manufacturers to distributors, pharmacies, or hospitals.  
   - Functions: `create-shipment`, `update-shipment-status`, `get-shipment`.  
   - Purpose: Logs shipment events with timestamps and locations.  

4. **InventoryContract**: Manages stock levels at each supply chain node (distributors, pharmacies).  
   - Functions: `add-inventory`, `transfer-inventory`, `get-inventory`.  
   - Purpose: Ensures accurate stock tracking and prevents overstocking.  

5. **AuthenticityContract**: Verifies product authenticity using cryptographic hashes.  
   - Functions: `verify-product-hash`, `store-product-hash`.  
   - Purpose: Prevents counterfeit products by validating hashes against registered products.  

6. **ComplianceContract**: Logs regulatory compliance data for audits.  
   - Functions: `log-compliance`, `get-compliance-report`, `verify-compliance`.  
   - Purpose: Provides immutable proof of adherence to regulations.  

### 🧑‍💼 For Stakeholders

- **Manufacturers**:  
  - Register via `ManufacturerRegistry`.  
  - Create products with unique IDs and hashes in `ProductRegistry`.  
  - Initiate shipments using `ShipmentContract`.  

- **Distributors/Pharmacies**:  
  - Update shipment status in `ShipmentContract`.  
  - Manage stock levels via `InventoryContract`.  
  - Verify product authenticity using `AuthenticityContract`.  

- **Regulators**:  
  - Access compliance records via `ComplianceContract`.  
  - Verify product provenance and authenticity.  

- **End-Users (Hospitals/Patients)**:  
  - Scan product QR codes to verify authenticity and view supply chain history.  

### 🚀 Getting Started

1. **Prerequisites**:  
   - Stacks blockchain environment (testnet or mainnet).  
   - Clarity development tools (e.g., Clarinet).  
   - Node.js for front-end integration (optional).  

2. **Deployment**:  
   - Deploy the 6 smart contracts using Clarinet.  
   - Configure authorized keys for manufacturers and regulators.  

3. **Usage**:  
   - Manufacturers: Call `register-manufacturer` and `register-product`.  
   - Distributors: Use `create-shipment` and `update-inventory`.  
   - Verifiers: Query `verify-product` or `get-compliance-report`.  

4. **Front-End (Optional)**:  
   - Build a web app to interact with contracts (e.g., using Stacks.js).  
   - Display product history, shipment status, and compliance reports.  

### 🛠 Example Workflow

1. A manufacturer registers a new drug batch:  
   - Calls `register-product` with product ID, name, batch number, and SHA-256 hash.  
2. The product is shipped to a distributor:  
   - Manufacturer calls `create-shipment` with shipment details.  
   - Distributor updates status in `ShipmentContract`.  
3. A pharmacy receives the shipment:  
   - Updates `InventoryContract` and verifies product via `AuthenticityContract`.  
4. A regulator audits the supply chain:  
   - Queries `ComplianceContract` for immutable logs.  
5. A patient scans a QR code:  
   - Verifies product authenticity and views supply chain history.  

### 🔐 Security Features

- **Immutable Records**: All data is stored on the Stacks blockchain.  
- **Permissioned Access**: Only authorized principals can execute sensitive functions.  
- **Cryptographic Verification**: Product hashes ensure authenticity.  
- **Auditability**: Compliance logs are transparent and tamper-proof.  

### 🌟 Why This Matters

- **Real-World Problem**: Counterfeit drugs cause thousands of deaths annually, and supply chain inefficiencies lead to shortages.  
- **Solution**: This project ensures end-to-end traceability, reduces fraud, and improves trust in the medical supply chain.  
- **Scalability**: The modular contract design supports additional features like IoT integration or real-time tracking.  

### 📚 Resources

- [Stacks Documentation](https://docs.stacks.co)  
- [Clarity Language Reference](https://docs.stacks.co/clarity)  
- [Clarinet Setup Guide](https://github.com/hirosystems/clarinet)  

Start building a transparent medical supply chain today! 🚀

