# w5_d5_hermes_agent_with_telegrambotHermes Agent – Telegram AI Operator
A self-hosted Hermes Agent running on a Hostinger VPS with OpenAI API, Telegram, web research, custom skills, server monitoring, and automated daily reporting.
🚀 Project Overview
This project turns Hermes Agent into a personal AI operator that can be accessed through Telegram.
                    ┌──────────────────┐
                    │     Telegram     │
                    │   AI Assistant   │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │  Hermes Gateway  │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │   Hermes Agent   │
                    └────────┬─────────┘
                             │
        ┌────────────────────┼────────────────────┐
        ▼                    ▼                    ▼
   Web Search          Terminal / Files       Memory
        │                    │                    │
        └────────────────────┼────────────────────┘
                             │
                  ┌──────────┴──────────┐
                  ▼          ▼          ▼
               AI News   SEO Trends  Server Health
                  └──────────┬──────────┘
                             ▼
                    Daily 9:00 AM Report
                             │
                             ▼
                         Telegram

🛠️ Technology Stack
- OS: Ubuntu 24.04.5 LTS
- Server: Hostinger VPS
- Architecture: x86_64
- Hermes Agent: v0.21.5
- Python: 3.14.7
- OpenAI SDK: 2.24.0
- LLM Provider: OpenAI API
- Model: GPT-4o-mini
- Messaging: Telegram
- Automation: Hermes Cron
- Timezone: Asia/Kolkata (IST)
- Web Research: Hermes Web Search
- Container Support: Docker
- Custom Skills: 3
📁 Hermes Configuration
Main Hermes directory:
/root/.hermes/

Important files:
/root/.hermes/
├── config.yaml
├── .env
├── SOUL.md
├── SOUL.md.backup
├── hermes-agent/
└── skills/
    ├── research/
    │   ├── ai-news/
    │   │   └── SKILL.md
    │   └── seo-trends/
    │       └── SKILL.md
    └── productivity/
        └── server-health/
            └── SKILL.md

Global operating rules:
/root/AGENTS.md

🤖 Telegram Integration
Hermes Gateway runs as a systemd service.
Service:
sudo systemctl status hermes-gateway

Restart if required:
sudo systemctl restart hermes-gateway

The Telegram bot is configured with an allowed Telegram user ID so unauthorized users cannot interact with the bot.
🧠 OpenAI Configuration
Hermes uses the OpenAI API.
Current provider:
openai-api

Current model:
gpt-4o-mini

Check configuration:
hermes config

Do not commit API keys, Telegram bot tokens, passwords, or other secrets to GitHub.
🛠️ Custom Skills
1. AI News
Location:
/root/.hermes/skills/research/ai-news/SKILL.md

Purpose:
- Search recent AI developments
- Focus on the latest 24 hours
- Prefer official sources
- Verify important claims
- Provide source-backed summaries
- Avoid fabricated or unverified news
2. SEO Trends
Location:
/root/.hermes/skills/research/seo-trends/SKILL.md

Purpose:
- Monitor recent SEO developments
- Google Search updates
- Search Console changes
- AI search developments
- Ranking/search changes
- Spam and algorithm developments
- Structured data and crawling/indexing updates
Google-specific claims should preferably use official Google sources.
3. Server Health
Location:
/root/.hermes/skills/productivity/server-health/SKILL.md

Purpose:
- CPU/load
- RAM
- Disk usage
- Uptime
- Failed services
- Hermes Gateway status
- Docker status
The skill is designed to perform read-only monitoring and does not restart or modify services.
⏰ Daily Automation
Cron Job:
Name: Daily AI SEO Server Briefing
Job ID: cef641c79b85
Schedule: 0 9 * * *
Timezone: Asia/Kolkata
Delivery: Telegram
Status: Active

The report contains:
1. AI News
2. SEO Trends
3. VPS Server Health
4. Important Warnings
5. Practical Action Items
Check cron jobs:
hermes cron list

Check scheduler:
hermes cron status

Run the job manually for testing:
hermes cron run cef641c79b85

Check previous runs:
hermes cron runs cef641c79b85

🔐 Security Rules
Never expose:
OpenAI API Key
Telegram Bot Token
SSH Private Keys
Passwords
.env files containing secrets

Before changing the VPS:
1. Check the current state.
2. Avoid unnecessary restarts.
3. Avoid unnecessary upgrades.
4. Never delete important files without confirmation.
5. Keep secrets outside Git repositories.
📊 Current Status
Component	Status
Hostinger VPS	✅ Working
Ubuntu	✅ 24.04.5 LTS
Hermes Agent	✅ Installed
OpenAI API	✅ Working
GPT-4o-mini	✅ Working
Telegram	✅ Working
Hermes Gateway	✅ Running
Web Search	✅ Enabled
Terminal	✅ Enabled
File Operations	✅ Enabled
Memory Tool	✅ Enabled
Skills	✅ Enabled
AI News Skill	✅ Working
SEO Trends Skill	✅ Working
Server Health Skill	✅ Working
Cron Scheduler	✅ Working
9:00 AM Daily Report	✅ Active
Telegram Delivery	✅ Working
Manual Cron Test	✅ Successful


🧪 Final Verification
The final cron test was successfully executed:
hermes cron run cef641c79b85

Result:
Triggered job: Daily AI SEO Server Briefing (cef641c79b85)
Next run: 2026-10-03T09:00:00+05:30
Ran now: succeeded.

This confirms that the complete daily automation pipeline is operational.
🎯 Future Enhancements
Possible next phases:
- Persistent user memory
- USER profile
- MCP servers
- External connectors
- Additional custom skills
- More Telegram commands
- Advanced server monitoring
- Additional scheduled reports
- Business/work automation
👨‍💻 Project Status
Status: Production-ready for the current configured workflow.
The core Hermes Telegram AI Operator is installed, configured, tested, and running on the Hostinger VPS.
Quick Commands
# Check Hermes
hermes config

# Check skills
hermes skills list

# Check gateway
sudo systemctl status hermes-gateway

# Check cron
hermes cron list

# Check scheduler
hermes cron status

# Test daily report
hermes cron run cef641c79b85

Project: Hermes Agent – Telegram AI Operator
Environment: Hostinger VPS / Ubuntu 24.04.5 LTS
Timezone: Asia/Kolkata (IST)
Daily Report: 9:00 AM IST
