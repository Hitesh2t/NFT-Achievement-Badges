# NFT Achievement Badges

A decentralized platform for issuing and managing NFT-based achievement certificates on the Stacks blockchain. This system allows organizations to create verifiable digital badges that recognize accomplishments, skills, or milestones.

## 🎯 Project Description

NFT Achievement Badges is a smart contract system that enables the creation and distribution of non-fungible token certificates. Each badge represents a unique achievement and contains metadata about the accomplishment, recipient, and issuing details. The system provides a transparent, immutable way to verify credentials and achievements on the blockchain.

## 🛠 Tech Stack Used

- **Blockchain**: Stacks (STX)
- **Smart Contract Language**: Clarity
- **Development Framework**: Clarinet
- **Wallet Integration**: Leather Wallet
- **NFT Standard**: SIP-009 (Stacks Improvement Proposal)

## 🚀 Setup Instructions

### Prerequisites
- [Clarinet](https://github.com/hirosystems/clarinet) installed
- [Leather Wallet](https://www.hiro.so/wallet) browser extension

### Local Development Setup

1. **Install Clarinet**
   
   #### On Windows
   winget install clarinet
   
   #### On macOS
   brew install clarinet
   
   #### On Linux
   curl -L https://github.com/hirosystems/clarinet/releases/latest/download/clarinet-linux-x64.tar.gz | tar xz
   ```

3. **Test the smart contract**
   ```bash
   clarinet check
   clarinet test
   ```

4. **Deploy to testnet**
   ```bash
   clarinet deployments generate --testnet --low-cost
   clarinet deployments apply --testnet
   ```

5. **Run the frontend** (if using local server)
   ```bash
   cd frontend
   # Simple HTTP server
   python -m http.server 8000
   # OR
   npx serve .
   ```

## 📝 Smart Contract Address

**Testnet Contract Address**: STWAW7GP2DKET1PR04AT02VFZJQ70PJ7SYTKNFC6
- Contract Name: `NFT-badges`
- Network: Stacks Testnet
- Transaction ID: 0x5131cdd63ec1a9a9706cf6c5404b1888dde9ce278adec82b6b37d747b0087a20

## 🎮 How to Use the Project

### For Achievement Issuers (Contract Owner)

1. **Deploy the Contract**: Use Clarinet to deploy to testnet/mainnet
2. **Award Badges**: Call `award-achievement-badge` function with:
   - Recipient's Stacks address
   - Badge title (max 64 characters)
   - Description (max 256 characters)
   - Achievement type (max 32 characters)
   - Optional image URI

### For Badge Recipients

1. **View Badges**: Use `get-user-badges` to see all badges owned
2. **Badge Details**: Call `get-badge-details` with badge ID for full information
3. **Transfer Badges**: Use standard NFT transfer functions (if transferrable)

### For Verification

1. **Verify Authenticity**: Anyone can verify badge details using the badge ID
2. **Check Statistics**: View achievement type statistics with `get-achievement-type-stats`

## 📱 Contract Functions

### Public Functions
- `award-achievement-badge`: Issues a new achievement badge
- `transfer`: Transfer badge ownership (SIP-009 standard)

### Read-Only Functions
- `get-badge-details`: Get comprehensive badge information
- `get-user-badges`: List all badges owned by a user
- `get-achievement-type-stats`: View statistics for achievement types
- `get-total-badges`: Get total number of badges issued
- `get-last-token-id`: Get the most recent badge ID
- `get-token-uri`: Get badge metadata URI
- `get-owner`: Get current badge owner

## 🏆 Features

- **SIP-009 Compliant**: Full compatibility with Stacks NFT standard
- **Metadata Storage**: Rich badge information stored on-chain
- **Achievement Tracking**: Statistics for different achievement types
- **User Collections**: Track badges owned by each user (max 50 per user)
- **Access Control**: Only contract owner can issue badges
- **Data Validation**: Comprehensive input validation and error handling

## 👥 Team Members

- **Hitesh Kumar Chandra** - Smart Contract Developer & Project Lead
- Role: Full-stack blockchain development, smart contract architecture

## 🖼 Screenshots & Demo

### Smart Contract Deployment
![alt text](<screeenshots/Screenshot 2025-08-17 162657.png>)


## 🔧 Development Notes

### Error Codes
- `u100`: Owner only operations
- `u101`: Not token owner
- `u102`: Invalid badge ID
- `u103`: Badge already exists
- `u104`: Unauthorized access
- `u105`: Invalid input data
- `u106`: Collection full (max 50 badges per user)

### Security Features
- Input validation for all parameters
- Access control for badge issuance
- Collection size limits to prevent spam
- Safe arithmetic operations
- Comprehensive error handling

## 🚀 Future Enhancements

- [ ] Badge revocation system
- [ ] Batch badge issuance
- [ ] Achievement categories management
- [ ] Integration with popular learning platforms
- [ ] Mobile app development
- [ ] IPFS integration for metadata storage