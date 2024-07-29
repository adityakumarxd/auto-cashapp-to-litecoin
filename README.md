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
3. Configure the config.json file:
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
4. Configure the hotwallet.json file:
```json
{
    "private_key": "LITECOIN_PRIVATE_KEY",
    "address": "LITECOIN_ADDRESS_ASSOCIATED_WITH_THE_PRIVATE_KEY"
}
```
5. Create and configure the webreceipts.txt file:
- This file will store receipt IDs from successful transactions to ensure that each receipt is used only once.

6. Important Note: The ltc2usd.json file is automatically updated by the bot to reflect current Litecoin to USD conversion rates. Do not modify this file manually.

7. Run the bot:

```bash
python bot.py
```


