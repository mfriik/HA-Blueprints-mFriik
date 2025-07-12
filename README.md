# Home Assistant Blueprints

This repository contains custom blueprints for [Home Assistant](https://www.home-assistant.io/) — a popular open-source platform for smart home automation.

---

## 📲 Confirmable Notification (Multi-Device)

This script blueprint sends a mobile actionable notification to **multiple devices**. It waits for the first response (confirmation or dismissal) and executes the corresponding action.

### 🔧 Features

- ✅ Sends notification to **multiple mobile devices**
- 🔔 Includes **Confirm** and **Dismiss** actions
- 🔄 Waits for **first device to respond**
- 🧩 Uses `context.id` to uniquely identify notification actions
- 🛠 Fully compatible with [Home Assistant’s mobile app integration](https://companion.home-assistant.io/)

### 🧱 Blueprint Info

- **Domain**: `script`
- **Mode**: `parallel` — allows multiple instances simultaneously
- **File**: `blueprints/script/YOUR_USERNAME/confirmable_notification_multi.yaml`

### 🔗 Import This Blueprint

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?repository_url=https://github.com/YOUR_USERNAME/home-assistant-blueprints/blob/main/blueprints/script/YOUR_USERNAME/confirmable_notification_multi.yaml)

Or manually paste this URL into Home Assistant ➝ *Blueprints* ➝ *Import Blueprint*:

