# 🤖 Agent Telegram Bot Skill

> Build intelligent Telegram bots with AI/LLM integration in minutes. Complete template for Claude Code — from setup to deployment.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![ Claude Code](https://img.shields.io/badge/Claude%20Code-Ready-brightgreen)](https://claude.ai/code)
[![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)](https://nodejs.org/)

## ✨ Features

- 🤖 **AI-Powered** — Integrate Claude, GPT, or any LLM seamlessly
- 💬 **Natural Conversations** — Context-aware responses with memory
- 🎯 **Command System** — Clean command handler with arguments parsing
- 🔄 **Message Types** — Text, photos, documents, stickers, locations
- 💾 **Conversation Memory** — SQLite/JSON persistence for context
- 🔗 **Webhook Support** — Production-ready with webhooks
- 📊 **Analytics** — Track usage, commands, errors

## 🚀 Quick Start

```bash
# Install the skill
claude-code skill install agent-telegram-bot-skill

# Create your first bot
claude-code "Create an AI chatbot that answers questions about my product"
```

## 💡 What This Does

```
claude-code "Create a Telegram bot that:
- Responds to /start with a welcome message
- Uses /ask <question> to query an AI
- Remembers conversation context
- Saves chat history to database"
```

## 🎯 Example Bots You Can Build

| Bot Type | Commands | Features |
|----------|----------|----------|
| AI Assistant | `/ask`, `/clear` | LLM-powered Q&A |
| Newsletter | `/subscribe`, `/send` | Broadcast messages |
| Customer Support | `/help`, `/ticket` | Ticket system |
| Content Bot | `/search`, `/latest` | Content aggregation |
| Reminder Bot | `/remind`, `/list` | Scheduled reminders |

## 🧩 Project Structure

```
agent-telegram-bot-skill/
├── skill.md                 # Main skill definition
├── bot.js                   # Core bot engine
├── handlers/
│   ├── commands.js          # Command handlers
│   ├── messages.js          # Message processors
│   └── callbacks.js         # Inline keyboard callbacks
├── ai/
│   ├── claude.js            # Claude API integration
│   └── memory.js            # Conversation memory
├── database/
│   ├── sqlite.js            # SQLite adapter
│   └── schemas.js           # Database schemas
├── examples/
│   ├── ai-chatbot.js        # AI chatbot template
│   ├── newsletter-bot.js    # Newsletter template
│   └── support-bot.js       # Support bot template
└── config/
    └── config.example.js    # Configuration template
```

## 🔧 Setup

1. **Get your Bot Token** from [@BotFather](https://t.me/BotFather)

2. **Create your bot:**
```bash
cp config/config.example.js config/config.js
# Edit config.js with your token
```

3. **Add your API key:**
```javascript
// config/config.js
module.exports = {
  telegram: {
    token: 'YOUR_BOT_TOKEN_HERE'
  },
  ai: {
    provider: 'claude', // or 'openai', 'gemini'
    apiKey: process.env.AI_API_KEY
  }
}
```

4. **Run:**
```bash
npm install
npm start
```

## 📱 Commands Reference

| Command | Description |
|---------|-------------|
| `/start` | Start the bot |
| `/help` | Show help |
| `/ask <text>` | Ask the AI |
| `/clear` | Clear conversation |
| `/stats` | View usage stats |

## 🎨 Customization

```javascript
// Add custom commands
bot.onCommand('/mycommand', async (ctx) => {
  await ctx.reply('Custom response!');
});

// Add inline keyboards
bot.onCommand('/menu', async (ctx) => {
  await ctx.reply('Choose an option:', {
    reply_markup: {
      inline_keyboard: [
        [{ text: 'Option 1', callback_data: 'opt1' }],
        [{ text: 'Option 2', callback_data: 'opt2' }]
      ]
    }
  });
});
```

## 🤖 AI Integration

### Claude (Recommended)
```javascript
const { ClaudeAI } = require('./ai/claude');

const ai = new ClaudeAI({
  apiKey: process.env.CLAUDE_API_KEY,
  model: 'claude-sonnet-4-6',
  maxTokens: 1024
});
```

### OpenAI
```javascript
const { OpenAI } = require('./ai/openai');

const ai = new OpenAI({
  apiKey: process.env.OPENAI_API_KEY,
  model: 'gpt-4'
});
```

## 📊 Analytics Dashboard

The bot tracks:
- Total messages processed
- Commands used
- AI queries
- Active users
- Error rate

Access via `/stats` command or built-in admin panel.

## 🚀 Deployment

### Railway
```bash
railway init
railway up
```

### Docker
```bash
docker build -t telegram-bot .
docker run -d --env-file .env telegram-bot
```

### VPS (PM2)
```bash
npm install -g pm2
pm2 start bot.js --name my-bot
pm2 save
```

## 🤝 Contributing

Issues and PRs welcome! Please read [CONTRIBUTING.md](./CONTRIBUTING.md)

## 📄 License

MIT © 2026 WebDev AI Pro

---

**⭐ If this helps you, consider buying me a coffee!** ☕

[!["Buy Me A Coffee"](https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&emoji=&slug=webdevaipro&button_color=%23FFDD00&outline_color=%23000000&logo_color=%23000000)](https://ko-fi.com/webdevaipro)
