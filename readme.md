**Payroll Protocol** is a confidential money distribution platform built on top of BNB , designed to provide confidentiality during the distribution of funds on-chain. By leveraging FHE cryptography and smart contracts, Payroll Protocol ensures the **confidentiality**, security, and efficiency of money distribution.

## Overview

Payroll Protocol integrates **BuidlGuidl BICONOMY AA SDK, BNB and INCO FHEVM** to enhance user experience while confidentially distributing money.

INCO FHEVM provides hidden states to store encrypted addresses that hold encrypted amounts on the INCO network, ensuring that all **transactions are secure and confidential**. This integration guarantees that money distribution details and recipient information remain confidential. It uses **modified Hyperlane infrastructure** to bridge these state values from BNB to INCO and vice versa.

## Key Features

1. **Encrypted USDC Distributions:** Protects sensitive information with robust encryption methods.
2. **User-Friendly Interface:** Simplifies the payroll process with one click, thanks to BICONOMY SDK.
3. **Stealth Hold:** Users can hold stablecoins for an indefinite amount of time without revealing the amount.
4. **Underline Distribution:** Users can completely hide their withdrawals by distributing the encrypted amount to different encrypted addresses on their behalf, providing an experience similar to Tornado Cash.

## Tech Stack

- **Frontend:** Next.js, BuidlGuidl, Tailwind CSS, 
- **Authentication & Wallets:** Privy
- **Backend & Smart Contracts:** Node.js, Solidity
- **Blockchain:** Bnb, INCO FHEVM
- **Account Abstraction & Gasless Transactions:** Biconomy
- **Encryption:** FHE schemes
- **Bridge** Hyperlane 


## Usage

1. Connect your web3 wallet.
2. Navigate to the distribution page.
3. Enter the recipient addresses and amounts.
4. Confirm the transaction to distribute funds confidentially.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## TFHE functions examples: 
```javascript
      mapping(eaddress => euint32) private ownerToBalance;

    // Encrypt a plaintext address to eaddress
    function encryptAddress(address plainAddress) public returns (eaddress) {
        return asEaddress(plainAddress);
    }

      function decryptAddress(eaddress _eAddress) public view returns (address) {
        // Decrypt the encrypted address
        return TFHE.decrypt(_eAddress);
    }

    function encryptAmount(uint32 amount) public view returns (euint32) {
        // Decrypt the encrypted address
        return TFHE.asEuint32(amount);
    }

     function decryptAmount(euint32 encryptedAmount) public view returns (uint32) {
        // Decrypt the encrypted address
        return TFHE.decrypt(encryptedAmount);
    }
```

## Acknowledgements

- [BNB](https://www.bnbchain.org/en)
- [BuidlGuidl](https://buidlguidl.com/)
- [Biconomy](https://www.biconomy.io/)
- [INCO FHEVM](https://inco.org/)
