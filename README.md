# amazon-refund-n8n-deepseek
AI-assisted workflow that tracks Amazon price drops and drafts refund requests automatically.  
Built using [n8n](https://n8n.io/), [DeepSeek](https://www.deepseek.com/), and PostgreSQL.

---

## Overview

Sometimes you buy something on Amazon, only to see it cheaper a week later.  
Amazon does not automatically refund you the difference, but if you catch it within the 30-day return window, you can usually request one.

This workflow automates that process.

It:
1. Checks your recent Amazon orders (via Gmail or API).
2. Scrapes the current item price.
3. Compares it to your purchase price.
4. Uses DeepSeek AI to summarize the change and generate a ready-to-send refund message.

---

## How It Works

| Step | Node | Description |
|------|------|--------------|
| 1 | Gmail Trigger | Detects new Amazon order emails. |
| 2 | Amazon Scraper | Retrieves current product prices. |
| 3 | PostgreSQL Node | Stores order history and previous checks. |
| 4 | DeepSeek Node | Creates refund summaries and draft messages. |
| 5 | Email / Notification Node | Sends alerts or refund drafts to you. |

You can customize the nodes, add your own triggers (such as Slack, Discord, or Telegram), or plug in other AI models.

---

## Quick Start

### 1. Clone this repository
```bash
git clone https://github.com/choihyerin/amazon-refund-n8n-deepseek.git
cd amazon-refund-n8n-deepseek
