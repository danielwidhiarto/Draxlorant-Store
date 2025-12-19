<div align="center">

# 🎮 DraxLorant Store Bot

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Discord](https://img.shields.io/badge/Discord-Bot-7289DA?logo=discord&logoColor=white)](https://discord.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

**A powerful Discord bot for checking your Valorant daily store without logging into the game!**

[Features](#-features) • [Installation](#-installation) • [Commands](#-commands) • [Configuration](#%EF%B8%8F-configuration) • [Contributing](#-contributing)

</div>

---

## 📋 About

DraxLorant Store Bot is a Discord bot built with Python that allows you to check your Valorant daily shop directly from Discord. No need to open the game - just use a simple slash command and get your daily store displayed beautifully on your Discord server!

The bot uses the official Valorant API to fetch store data securely and supports multiple display designs to match your preferences.

## ✨ Features

- 🛒 **Daily Store Checker** - View your Valorant daily shop rotation without opening the game
- 🔐 **Secure Authentication** - Uses official Valorant API with secure token management
- 🎨 **Multiple Display Designs** - Choose between different embed styles for your store
- 🔔 **Store Notifications** - Get notified when specific skins appear in your store
- 💾 **Account Management** - Save your credentials for quick access (with encryption)
- ⚡ **Temporary Login** - Check store without saving credentials using temporary authentication
- 🔄 **Auto-Update** - Automatically fetches latest skin data and pricing
- 🌍 **Multi-Region Support** - Works with all Valorant regions (NA, EU, AP, KR, etc.)
- 📊 **Beautiful Image Generation** - Custom-designed store cards with skin images and pricing

## 🚀 Installation

### Prerequisites

- Python 3.8 or higher
- Discord Bot Token
- Valorant/Riot Games Account

### Step 1: Clone the Repository

```bash
git clone https://github.com/danielwidhiarto/Draxlorant-Store.git
cd Draxlorant-Store
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 3: Configure the Bot

1. Create your Discord bot on the [Discord Developer Portal](https://discord.com/developers/applications)

   - Go to "Bot" section and create a new bot
   - Copy the bot token
   - Enable necessary intents (Server Members Intent, Message Content Intent)
   - Generate OAuth2 URL with `bot` and `applications.commands` scopes

2. Edit `config.json` file:

   ```json
   {
     "TOKEN": "YOUR_DISCORD_BOT_TOKEN_HERE",
     "notify_mode": "Spectified",
     "embed_design": "ꜱᴛᴀᴄɪᴀ.#7475",
     "store_password": false,
     "refresh_token": true
   }
   ```

   **Configuration Options:**

   - `TOKEN`: Your Discord bot token
   - `notify_mode`: Notification mode (`"Spectified"` or `"All"`)
   - `embed_design`: Choose display style (`"ꜱᴛᴀᴄɪᴀ.#7475"` or `"Giorgio#0609"`)
   - `store_password`: Store passwords locally (set to `false` for security)
   - `refresh_token`: Auto-refresh authentication tokens

### Step 4: Run the Bot

```bash
python bot.py
```

## 🎯 Commands

### Main Commands

| Command                        | Description                        | Usage                                         |
| ------------------------------ | ---------------------------------- | --------------------------------------------- |
| `/store`                       | Display your daily Valorant store  | `/store`                                      |
| `/store [username] [password]` | Check store with temporary login   | `/store username:player@riot password:******` |
| `/login`                       | Save your Riot account credentials | `/login`                                      |
| `/logout`                      | Remove your saved credentials      | `/logout`                                     |
| `/notify add`                  | Add skin to notification list      | `/notify add [skin name]`                     |
| `/notify list`                 | View your notification list        | `/notify list`                                |
| `/notify remove`               | Remove skin from notifications     | `/notify remove [skin name]`                  |

### Usage Examples

**Check your store (with saved credentials):**

```
/store
```

**Check store without saving credentials:**

```
/store username:yourname@tag password:yourpassword
```

**Set up notifications:**

```
/notify add Prime Vandal
```

## ⚙️ Configuration

### Bot Settings

The `config.json` file controls bot behavior:

- **TOKEN**: Your Discord bot token (required)
- **notify_mode**:
  - `"Spectified"` - Notify only for specific skins you've added
  - `"All"` - Notify for all items in store
- **embed_design**: Choose between different visual styles
  - `"ꜱᴛᴀᴄɪᴀ.#7475"` - Image-based design with custom background
  - `"Giorgio#0609"` - Embed-based design with multiple cards
- **store_password**: Store encrypted credentials locally
- **refresh_token**: Automatically refresh authentication tokens

### Region Support

The bot automatically detects your region based on your Riot account. Supported regions:

- NA (North America)
- EU (Europe)
- AP (Asia Pacific)
- KR (Korea)
- BR (Brazil)
- LATAM (Latin America)

## 🔒 Security & Privacy

**⚠️ IMPORTANT SECURITY NOTICE:**

1. **Never share your `config.json` file** - It contains your bot token
2. **Use refresh tokens** - Set `refresh_token: true` to avoid storing passwords
3. **Temporary login recommended** - Use `/store username password` for one-time checks
4. **Token encryption** - User tokens are stored with encryption
5. **No API key required** - Unlike the old README, Riot API keys are not needed for this bot

> **Note:** This bot does not violate Riot's Terms of Service as it uses the official authentication methods. However, sharing accounts or using third-party access is always at your own risk.

## 📁 Project Structure

```
Draxlorant-Store/
├── bot.py              # Main bot file
├── config.json         # Configuration file
├── requirements.txt    # Python dependencies
├── cogs/
│   ├── valorant.py    # Valorant commands
│   └── notify.py      # Notification system
├── utils/
│   ├── auth.py        # Authentication handler
│   ├── store.py       # Valorant API wrapper
│   ├── pillow.py      # Image generation
│   └── useful.py      # Helper functions
└── assets/
    ├── images/        # Store background images
    └── font/          # Custom fonts for images
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Ideas for Contributions

- Add more embed design options
- Implement bundle/night market checking
- Add weapon stats and information
- Create a web dashboard
- Add more languages support
- Improve error handling

## ❓ FAQ

<details>
<summary><b>Why isn't my bot responding?</b></summary>

Make sure you've:

- Enabled the bot with proper permissions
- Invited the bot with `applications.commands` scope
- Enabled Message Content Intent in Discord Developer Portal
- Correctly set your bot token in `config.json`
</details>

<details>
<summary><b>Is this bot safe to use?</b></summary>

Yes, the bot uses official Riot authentication. However, always be cautious when providing account credentials. Consider using temporary login instead of saving credentials.

</details>

<details>
<summary><b>Can I host this bot 24/7?</b></summary>

Yes! You can deploy this bot on platforms like:

- Heroku (use the included `Procfile`)
- Railway
- DigitalOcean
- AWS/Google Cloud
- Your own VPS
</details>

<details>
<summary><b>My store images aren't loading</b></summary>

This usually happens when:

- Missing dependencies (install Pillow: `pip install Pillow`)
- Missing font files in `assets/font/`
- Skin data hasn't been cached yet (wait a few minutes after first run)
</details>

## 📝 Credits

- **Developer**: [Daniel Widhiarto](https://github.com/danielwidhiarto)
- **Embed Design**: ꜱᴛᴀᴄɪᴀ.#7475
- **Alternative Design**: [Giorgio](https://github.com/giorgi-o/)
- **Valorant API**: Unofficial Valorant API by the community

## 📄 License

This project is licensed under the [MIT License](LICENSE).

```
MIT License - Copyright (c) 2025
```

---

<div align="center">

**Made with ❤️ for the Valorant community**

⭐ Star this repo if you find it useful! ⭐

[Report Bug](https://github.com/danielwidhiarto/Draxlorant-Store/issues) • [Request Feature](https://github.com/danielwidhiarto/Draxlorant-Store/issues)

</div>
