**Stellar Split Bill Calculator**

A simple Stellar Testnet dApp that connects a Freighter wallet, displays the connected account's XLM balance, calculates an equal bill split among a group, and sends the resulting XLM payment on-chain — with clear success/failure feedback.

Built for Level 1 – White Belt: connecting a wallet, funding it, reading a balance, and sending a testnet transaction.


Project Description

Splitting a bill with friends usually takes two separate steps: figuring out who owes what, and then actually sending the money. Stellar Split Bill Calculator combines both into one flow on the Stellar network:


Connect your Freighter wallet (Stellar Testnet).
View your connected address and current XLM balance.
Enter the total bill amount and the number of people splitting it.
Enter the recipient's Stellar address.
Click Calculate & Send Payment — the app calculates the per-person share and submits an XLM payment transaction via Freighter.
See the transaction go from pending to a final success state, along with the transaction hash.


Features


🔗 Connect / disconnect a Freighter wallet
💰 Live XLM balance display, fetched from Stellar Testnet
🧮 Automatic bill-split calculation (total ÷ number of people)
💸 On-chain XLM payment via the Stellar SDK, signed in Freighter
✅ Real-time transaction status: pending → success/failure, with transaction hash shown to the user


Tech Stack


React (frontend)
Freighter Wallet + @stellar/freighter-api
@stellar/stellar-sdk (building/submitting payment transactions)
Stellar Testnet Horizon API (https://horizon-testnet.stellar.org)



Setup Instructions (Run Locally)

Prerequisites


Node.js v16 or later and npm
Freighter Wallet browser extension installed
A Freighter wallet account switched to Test Net (Freighter settings → Network → Test Net)
Some testnet XLM in that account (use Friendbot to fund it if the balance is 0)


1. Clone the repository

bashgit clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>

2. Install dependencies

bashnpm install

3. Configure environment (if applicable)

If the project uses a .env file for network configuration, create one in the root directory:

bashREACT_APP_STELLAR_NETWORK=TESTNET
REACT_APP_HORIZON_URL=https://horizon-testnet.stellar.org


If your project has network settings hard-coded in a config file instead, note that here and skip this step.



4. Start the app

bashnpm start

The app will run locally at:

http://localhost:3000

(adjust the port to whatever your app actually uses, e.g. 3002)

5. Connect your wallet


Open the app in your browser.
Click Connect Wallet.
Approve the connection request in the Freighter popup.
Your connected address and XLM balance will appear.


6. Try a split payment


Enter a total bill amount and number of people.
Enter a recipient Stellar testnet address.
Click Calculate & Send Payment.
Approve the transaction in the Freighter popup.
Watch the status change from Transaction Pending to Transaction Successful, with the transaction hash displayed.



**Screenshots**

**level_01 screenshots folder**



Project Structure (example)

├── src/
│   ├── components/
│   │   ├── WalletConnect.js
│   │   ├── BalanceDisplay.js
│   │   ├── SplitCalculator.js
│   │   └── TransactionResult.js
│   ├── utils/
│   │   └── stellar.js        # Horizon/network config, payment builder
│   └── App.js
├── screenshots/
├── package.json
└── README.md

Notes


This app runs entirely against the Stellar Testnet — no real funds are used.
If your Freighter account shows a 0 balance, fund it using Friendbot.
Transaction hashes can be looked up on Stellar Expert (Testnet).
