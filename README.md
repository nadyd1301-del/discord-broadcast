# Wick Studio - Discord Broadcast System

<div align="center">
  <img src="https://media.wickdev.me/IGG6cyadBh.png" alt="Wick Studio Logo" width="200"/>
  <br>
  <h3>🚀 Advanced Discord Broadcast System with Multi-Client Support</h3>
  <p>A powerful Discord broadcasting solution for large servers</p>
  
  ![Version](https://img.shields.io/badge/version-2.0.0-blue)
  ![License](https://img.shields.io/badge/license-MIT-green)
  ![Discord.js](https://img.shields.io/badge/discord.js-v13.12.0-7289da)
  ![Node.js](https://img.shields.io/badge/node.js-v16.x-43853d)
</div>

---

## 📋 Features

- **⚡ Multi-Client Broadcasting**: Utilizes multiple bot tokens to dramatically increase broadcasting speed
- **📊 Load Balancing**: Intelligently balances the workload across multiple bots
- **🚫 Rate Limit Management**: Avoids Discord's rate limits with configurable cooldowns
- **🌐 Multilingual Support**: Full support for both English and Arabic languages
- **📈 Real-time Progress Tracking**: Live progress updates while broadcasts are running
- **📱 Mobile-Friendly UI**: Clean and intuitive interface with buttons
- **📄 Detailed Reports**: Comprehensive broadcast reports with success/failure statistics
- **🛡️ Error Handling**: Robust error handling for failed message delivery

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/wickstudio/discord-broadcast.git
   cd discord-broadcast
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Create a `.env` file in the root directory and add your bot tokens:**
   ```
   DISCORD_TOKEN=your_main_bot_token
   DISCORD_TOKEN_2=your_second_bot_token
   ```

4. **Configure the settings in `config.js`**

5. **Start the bot**
   ```bash
   npm start
   ```

## ⚙️ Configuration

The bot is configured through the `config.js` file:

```javascript
module.exports = {
    bot: {
        tokens: [
            process.env.DISCORD_TOKEN,                  // Main bot token
            process.env.DISCORD_TOKEN_2,                // 2 bot token
        ].filter(Boolean),

        defaultLanguage: 'ar', // ar | en لغة البوت
        
        activity: {
            name: '📢 Wick Studio', // رسالة حالة البوت
            type: 'WATCHING', // PLAYING, STREAMING, LISTENING, WATCHING, COMPETING
            status: 'dnd' // online, idle, dnd, invisible
        }
    },
    server: {
        guildId: '1431637729036206145',                  // ايدي السيرفر
        broadcastRoleId: 'YOUR_BROADCAST_ROLE_ID',  // ايدي الرول اللي يستخدم عليها البوت
        reportChannelId: '1431637730470924399'   // ايدي الروم اللي يرسل فيه البوت التقارير
    },
    // Additional configuration...
}
```

## 🤖 Commands

| Command | Description |
|---------|-------------|
| `-bc <message>` | Start a broadcast with your message |
| `-language` | View and select a language |
| `-lang <en/ar>` | Change bot language directly |
| `-wick` | Test command to check bot status and server stats |

## 📢 Broadcast Options

The broadcast panel provides the following broadcast options:

- **👥 All Members**: Send to every member in the server
- **🟢 Online Members**: Send only to members who are currently online
- **⭕ Offline Members**: Send only to members who are offline
- **❌ Cancel**: Cancel the broadcast preparation

## 🏗️ Project Structure

```
.
├── index.js                      # Main entry point
├── config.js                     # Bot configuration
├── .env                          # Environment variables (bot tokens)
├── package.json                  # Project dependencies
└── src/
    ├── models/                   # Core functionality
    │   ├── BroadcastManager.js   # Manages multi-client broadcasting
    │   └── LanguageManager.js    # Handles multilingual support
    ├── controllers/
    │   └── BroadcastController.js # Handles commands and interactions
    ├── utils/
    │   └── helpers.js            # Utility functions
    └── locales/                  # Language files
        ├── en.json               # English translations
        └── ar.json               # Arabic translations
```

## 📊 Performance

The broadcast speed depends on the number of bot clients you've configured. Each additional bot multiplies your broadcasting capacity.

| Bots | Est. Members/second |
|------|---------------------|
| 1    | ~1                  |
| 2    | ~2                  |
| 5    | ~5                  |
| 10   | ~10                 |

## 🔍 Troubleshooting

### Common issues:

1. **"No bot tokens found in configuration"**
   - Make sure your `.env` file is set up correctly with valid bot tokens

2. **Rate limit errors**
   - Adjust the `cooldownTime` and `requestsPerSecond` in config.js

3. **Permission errors**
   - Ensure your bots have the "MESSAGE CONTENT" intent enabled in Discord Developer Portal
   - Verify that the bots have permission to read messages and send DMs

## 🔮 Future Plans

- Support for embeds in broadcasts
- Custom broadcast templates
- Web dashboard for advanced analytics
- Scheduled broadcasts

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🔗 Links

- [Discord Server](https://discord.gg/wicks)
- [GitHub Repository](https://github.com/wickstudio/discord-broadcast)

## 👨‍💻 Credits


Developed with 💜 by [Wick Studio](https://discord.gg/wicks) 
