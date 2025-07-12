# HA-Blueprints-mFriik

Custom Home Assistant blueprint for sending actionable notifications to **multiple mobile devices** — with auto-clear support once any device responds. Fully customizable and ideal for multi-user household interactions.

---

## 📲 Confirmable Notification (Multi-Device)

This blueprint sends a notification to one or more `mobile_app` devices. As soon as **any** recipient confirms or dismisses, it:

1. Triggers the **confirm** or **dismiss** action you define  
2. **Clears** the notification from **all** devices  
3. Supports an **optional custom tag** for advanced behavior

---

### 🔧 Features

- Notify multiple devices  
- Unique confirm/dismiss logic per script execution  
- Clears notifications across all devices once handled  
- Optional custom tag support via UI  
- Safe to use in parallel script mode  

---

## 🧱 Blueprint Info

- **Domain**: `script`  
- **Mode**: `parallel`  
- **File Path**: `blueprints/script/mfriik/confirmable_notification_multi.yaml`  
- **Source URL**: [Blueprint File](https://github.com/mfriik/HA-Blueprints-mFriik/blob/main/blueprints/script/mfriik/confirmable_notification_multi.yaml)

---

### 🛠️ Import This Blueprint

Click below to import directly into your Home Assistant instance:

<a href="https://my.home-assistant.io/redirect/blueprint_import/?repository_url=https://raw.githubusercontent.com/mfriik/HA-Blueprints-mFriik/main/blueprints/script/mfriik/confirmable_notification_multi.yaml">
  <img src="https://community-assets.home-assistant.io/original/4X/1/a/1/1a129e306bc6a339cf8a2b9222553254a1909b6f.svg" 
       alt="Import this blueprint" width="592" height="40" style="max-width: 100%;">
</a>

---

## ⚙️ Usage Instructions

1. Select one or more `notify.mobile_app_*` services under **Devices to notify**
2. Provide:
   - Notification title and message  
   - Button text for Confirm and Dismiss  
   - A **required unique tag** (used to group/clear the notification)
3. Optionally:
   - Add actions to run on Confirm or Dismiss  
   - Customize follow-up messages and log entries  
   - Set a timeout in minutes  

---

## 🧪 Example Use Case

```yaml
alias: Prompt Household to Start Cleaning
use_blueprint:
  path: mfriik/confirmable_notification_multi.yaml
  input:
    notify_devices:
      - service: notify.mobile_app_michals_iphone
      - service: notify.mobile_app_partners_pixel
    notification_tag: vacuum_confirm
    decision_title: "Start Cleaning?"
    decision_message: "Should the vacuum start now?"
    decision_confirm_title: "Yes"
    decision_dismiss_title: "No"
    confirm_actions:
      - service: vacuum.start
        target:
          entity_id: vacuum.roborock
    dismiss_actions:
      - service: input_boolean.turn_on
        target:
          entity_id: input_boolean.skip_vacuum_today
