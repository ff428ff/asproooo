# MTA:SA Money Discord Bot

A Discord bot that allows you to manage player money in an MTA:SA server through Discord commands.

## Features

- Check a player's money balance
- Add, remove, or set a player's money
- View the top richest players on the server

## Prerequisites

- Node.js 16.9.0 or higher
- MySQL database for your MTA:SA server
- Discord Bot Token

## Setup

1. Clone this repository
2. Install dependencies:
   ```
   npm install
   ```
3. Create a `.env` file based on the `.env.example` template and fill in your details:
   ```
   # Discord Bot Configuration
   BOT_TOKEN=your_discord_bot_token_here
   CLIENT_ID=your_client_id_here

   # MySQL Database Configuration
   DB_HOST=localhost
   DB_PORT=3306
   DB_USER=your_mysql_username
   DB_PASSWORD=your_mysql_password
   DB_NAME=mta_database

   # Server Configuration
   PREFIX=!
   ```

## Database Requirements

This bot assumes your MTA:SA server database has an `accounts` table with at least these columns:
- `username` - The player's username
- `money` - The player's money amount

If your database structure is different, you'll need to modify the queries in `database.js`.

## Deploy Commands

You need to register the slash commands with Discord:

```
node deploy-commands.js
```

## Start the Bot

```
npm start
```

Or for development:

```
npm run dev
```

## Commands

- `/money [username]` - Check how much money a player has
- `/setmoney [username] [amount] [action]` - Set, add, or remove money from a player
- `/topmoney [limit]` - Show the top richest players on the server

## Permissions

- `/money` and `/topmoney` can be used by any member
- `/setmoney` requires Administrator permissions

## License

MIT 