# Freetime Maker Shop

The Official Online Shop from Freetime Maker with integrated cryptocurrency payment processing using the FreetimeSDK.

## 🚀 Features

- **Multi-Cryptocurrency Support**: Accept payments in Bitcoin, Ethereum, Litecoin, and more
- **Secure Payment Processing**: Built with the official FreetimeSDK for secure transactions
- **Fee Management**: Transparent fee structure with developer fee support
- **Address Validation**: Built-in address validation for all supported cryptocurrencies
- **Real-time Balance Checking**: Monitor shop wallet balances
- **Developer-Friendly**: Easy to integrate and extend

## 💳 Supported Cryptocurrencies

- **Bitcoin (BTC)** - The original cryptocurrency
- **Ethereum (ETH)** - Smart contract platform
- **Litecoin (LTC)** - Faster Bitcoin alternative
- **Bitcoin Cash (BCH)** - Bitcoin fork with larger blocks
- **Dogecoin (DOGE)** - Popular meme cryptocurrency
- **Solana (SOL)** - High-performance blockchain
- **Polygon (MATIC)** - Ethereum scaling solution
- **Binance Coin (BNB)** - Exchange token
- **Tron (TRX)** - Decentralized entertainment platform

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/FreetimeMaker/Freetime-Maker-Shop.git
cd Freetime-Maker-Shop

# Install dependencies
npm install

# Start the shop
npm start
```

For development with hot reload:
```bash
npm run dev
```

## 🔧 Usage

### Basic Shop Setup

```javascript
const { FreetimeMakerShop } = require('./main.js');

// Initialize the shop
const shop = new FreetimeMakerShop();

// Shop wallets are automatically created for Bitcoin, Ethereum, and Litecoin
```

### Processing Payments

```javascript
// Process a Bitcoin payment
const customerAddress = '1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa';
const amount = '0.001';
const currency = 'Bitcoin';

try {
    const result = await shop.processPayment(currency, amount, customerAddress);
    const txHash = await result.broadcast();
    console.log(`Payment successful: ${txHash}`);
} catch (error) {
    console.error('Payment failed:', error.message);
}
```

### Validating Addresses

```javascript
// Validate a Bitcoin address
const isValid = await shop.validatePaymentAddress(
    '1A1zP1eP5QGefi2DMPTfTL5SLmv7DivfNa', 
    'Bitcoin'
);
console.log(`Address valid: ${isValid}`);
```

### Checking Balances

```javascript
// Check shop's Bitcoin balance
const balance = await shop.checkShopBalance('Bitcoin');
console.log(`Shop Bitcoin balance: ${balance} BTC`);
```

### Getting Supported Cryptocurrencies

```javascript
const supportedCoins = shop.getSupportedCryptocurrencies();
console.log('Supported payments:', supportedCoins);
```

## 💰 Fee Structure

The SDK implements a tiered fee structure to support ongoing development:

| Transaction Amount | Fee Percentage | Tier |
|-------------------|----------------|------|
| ≥ 1000 | 0.05% | Enterprise |
| ≥ 100 | 0.1% | Business |
| ≥ 10 | 0.25% | Professional |
| ≥ 1 | 0.35% | Standard |
| ≥ 0.1 | 0.4% | Basic |
| < 0.1 | 0.5% | Micro |

## 🔒 Security Features

- **Local Cryptographic Operations**: All operations performed locally
- **Private Key Security**: Private keys never leave your application
- **Address Validation**: Comprehensive validation for all supported cryptocurrencies
- **Secure Random Generation**: Secure random number generation for wallet creation

## 🏗️ Project Structure

```
Freetime-Maker-Shop/
├── main.js                 # Main shop implementation
├── package.json            # Dependencies and scripts
├── README.md              # This file
└── node_modules/          # Dependencies (including freetimesdk)
```

## 🚀 Getting Started

1. **Install Dependencies**: Run `npm install` to install the FreetimeSDK and other dependencies
2. **Run the Demo**: Execute `npm start` to see the demo in action
3. **Integrate**: Use the `FreetimeMakerShop` class in your application
4. **Customize**: Extend the shop class to fit your specific needs

## 📚 API Reference

### FreetimeMakerShop Class

#### Methods

- `processPayment(coinType, amount, customerAddress)` - Process a cryptocurrency payment
- `validatePaymentAddress(address, coinType)` - Validate a cryptocurrency address
- `checkShopBalance(coinType)` - Check shop's balance for a specific cryptocurrency
- `getSupportedCryptocurrencies()` - Get list of supported cryptocurrencies
- `getFeeStructure()` - Get the fee structure information

### FreetimeSDK Integration

The shop uses the official FreetimeSDK which provides:

- **Wallet Management**: Create and manage cryptocurrency wallets
- **Transaction Processing**: Send and receive cryptocurrency payments
- **Fee Estimation**: Calculate transaction fees before sending
- **Balance Checking**: Check wallet balances in real-time

## 🛠️ Development

### Adding New Features

To extend the shop functionality:

1. Modify the `FreetimeMakerShop` class in `main.js`
2. Add new methods for your specific needs
3. Update the README with new features

### Testing

```bash
# Run the demo to test functionality
npm start

# For development with file watching
npm run dev
```

## 📄 License

This project is licensed under the Apache License 2.0 - see the LICENSE file for details.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 Support

For support:
- Open an issue on the GitHub repository
- Contact the Freetime Maker team
- Check the [FreetimeSDK documentation](https://github.com/FreetimeMaker/FreetimeSDK-NPM)

## 🔗 Related Projects

- [FreetimeSDK](https://github.com/FreetimeMaker/FreetimeSDK) - The original Android SDK
- [FreetimeSDK-NPM](https://www.npmjs.com/package/freetimesdk) - The Node.js version used in this project

---

**Built with ❤️ by Freetime Maker**
