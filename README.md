# Auto Cashapp to Litecoin Bot

## Overview
The Auto Cashapp to Litecoin Bot is a Discord bot designed to facilitate the conversion of CashApp funds to Litecoin. Users can interact with the bot through Discord commands and buttons, making the process seamless and automated.

## Features
- Ticket System: Create and manage support tickets.
- CashApp to Litecoin Conversion: Convert funds from CashApp to Litecoin.
- Dynamic Button Interactions: Use Discord buttons for user interactions.
- Customizable Configuration: Easily configure bot settings through JSON files.

## Setup
### Prerequisites
1. Python: Ensure you have Python 3.8 or later installed.
2. Discord Bot Token: Create a bot on [Discord Developer Portal](https://discord.com/developers/applications) and get your token.
3. Tatum API Key: Obtain an API key from [Tatum](https://dashboard.tatum.io/) for handling Litecoin transactions.

### Installation
1. Clone the repository:
```bash
git clone https://github.com/adityakumarxd/auto-cashapp-to-litecoin.git
cd auto-cashapp-to-litecoin
```
2. Install the required Python packages:
```bash
pip install -r requirements.txt
```
3. Configure the `config.json` file:
```json
{
    "bot_token": "YOUR_DISCORD_BOT_TOKEN",
    "ltc_transaction_fees": 0.00014,
    "tatum_api_key": "YOUR_TATUM_API_KEY",
    "ticket_channel_id": "TICKET_CHANNEL_ID",
    "ticket_category_id": "TICKET_CATEGORY_ID",
    "cashapp_id": "YOUR_CASHAPP_ID"
    "exchange_fee_percentage": 5,
    "owner_ids": [USER_ID_1, USER_ID_2, USER_ID_3...]

}
```
4. Configure the `hotwallet.json` file:
```json
{
    "private_key": "LITECOIN_PRIVATE_KEY",
    "address": "LITECOIN_ADDRESS_ASSOCIATED_WITH_THE_PRIVATE_KEY"
}
```
5. Configure `stats.json` file:
```json
{
    "total_deals": 0,
    "total_amount": 0
}
```
7. Create and configure the `webreceipts.txt` file:
- This file will store receipt IDs from successful transactions to ensure that each receipt is used only once.

7. Important Note: The `ltc2usd.json` file is automatically updated by the bot to reflect current Litecoin to USD conversion rates. Do not modify this file manually.

8. Run the bot:

```bash
python bot.py
```

## How It Works
### 1. Interaction with the Bot:

- Creating Tickets: Users can create a ticket by clicking a button, which generates a new private channel where the user can interact with the bot.
- CashApp to Litecoin Conversion:
    - Initiate Conversion: After creating a ticket, users can start the conversion process by clicking the Proceed button.
    - Enter Amount: The bot prompts users to enter the amount in USD that they want to convert.
    - Confirm Amount: Users confirm the amount, and the bot calculates the equivalent Litecoin value.
    - Enter CashApp Receipt URL: Users provide a CashApp receipt URL. The bot validates the URL and processes it.
    - Enter Litecoin Address: Users input their Litecoin address where the converted funds will be sent.
    - Send Litecoin: The bot sends the Litecoin to the provided address using the Tatum API.
- End of Process: After the conversion, the bot sends a confirmation message and closes the ticket channel.

### 2. Commands:
- `/ping`: Displays the bot's ping in an embed.
- `/addbal`: Shows the hot wallet address and balance. Allows adding balance to the hot wallet.
- `/changeca`: Updates the CashApp ID in `config.json`.
- `/stats`: Displays the bot's statistics, including the total number of deals completed and the total amount of deals.

### 3. Buttons:
- Proceed: Starts the conversion process. Opens a modal to input the amount in USD.
- Close: Closes the ticket and disables all buttons. No further actions can be taken.
- Confirm: Confirms the exchange amount and provides instructions for payment.
- Reset: Resets the process, allowing the user to input a new amount and starting the modal over.

## Configuration Files
- `config.json`: Contains bot settings including tokens, channel IDs, and API keys.
- `hotwallet.json`: Stores the hot wallet address for transactions.
- `stats.json`: Tracks the total number of deals completed and the total amount of deals.
- `webreceipts.txt`: Tracks receipt IDs to avoid duplication. Each receipt ID is stored here once used to ensure it is not reused.
- `ltc2usd.json`: Automatically updated by the bot with current Litecoin to USD conversion rates. Do not modify it manually.

