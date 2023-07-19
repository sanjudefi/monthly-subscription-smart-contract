
# MonthlySubscription Smart Contract

The MonthlySubscription smart contract is a Solidity contract that enables monthly subscription services with automatic deductions on the Ethereum blockchain. It allows users to subscribe to a service and automatically deducts the subscription amount each month until the subscription is canceled. The contract is designed to be integrated with Metamask for payment handling.

## Features

- Users can create monthly subscriptions by calling the `createSubscription` function.
- Subscribers can renew their subscriptions by calling the `renewSubscription` function, which automatically deducts the subscription amount from their Metamask wallet.
- Subscribers can cancel their subscriptions by calling the `cancelSubscription` function.
- The contract owner can withdraw the accumulated subscription funds using the `withdrawFunds` function.
- The contract supports ERC-20 tokens for payment (set during deployment).

## Getting Started

1. Clone the repository:

```bash
git clone https://github.com/your-username/MonthlySubscription.git
cd MonthlySubscription
```

2. Install dependencies (requires Node.js and npm):

```bash
npm install
```

3. Compile the smart contract:

```bash
npx hardhat compile
```

4. Test the smart contract:

```bash
npx hardhat test
```

## Deployment

1. Before deploying, configure the contract by setting the following parameters in the `MonthlySubscription.sol` file:

   - `tokenAddress`: The address of the ERC-20 token used for subscription payments.
   - `subscriptionAmount`: The monthly subscription amount in token units.
   - `paymentDay`: The day of the month when the payment is due (1 to 28).

2. Deploy the contract to the Ethereum blockchain using Hardhat or any other Ethereum development framework.

## Usage

Interact with the deployed smart contract using Web3 or any Ethereum wallet that supports contract interaction (e.g., Metamask).

### Functions

1. `createSubscription`: Creates a new monthly subscription for the caller. The subscription starts 30 days from the creation date.

2. `renewSubscription`: Renews the caller's subscription, deducting the subscription amount from the Metamask wallet. It also extends the subscription for the next 30 days.

3. `cancelSubscription`: Cancels the caller's subscription and stops the automatic deductions.

4. `deductSubscription` (optional): Automatically deducts the subscription amount for the caller's subscription. This function is intended to be called from Metamask by the subscriber.

5. `withdrawFunds` (only for contract owner): Allows the contract owner to withdraw the accumulated subscription funds.

## Security Considerations

- This is a simplified example for illustrative purposes and should not be used in a production environment without proper security audits and testing.
- Use ERC-20 tokens that are well-audited and secure for subscription payments.
- Ensure that the smart contract deployment process and integration with Metamask are secure to prevent any vulnerabilities.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

