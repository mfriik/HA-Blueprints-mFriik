# HA-Confirmable-Notification-for-Multiple-Devices

Custom Home Assistant blueprint for sending actionable notifications to **multiple mobile devices** — with auto-clear support once any device responds. Fully customizable and ideal for multi-user household interactions.

---

## 📲 Confirmable Notification (Multi-Device)

This blueprint sends a notification to one or more `mobile_app` devices. As soon as **any** recipient confirms or dismisses, it:

1. Triggers the **confirm** or **dismiss** action defined by you  
2. **Clears** the notification from **all** devices  
3. Supports an **optional custom tag** to identify or override the notification

---

### 🔧 Features

- Multiple device targeting  
- Unique confirm/dismiss handling per script run  
- Auto-clear across all devices  
- Optional custom tag via UI  
- Supports parallel script execution in Home Assistant

---

## 🧱 Blueprint Details

- **Domain**: `script`  
- **Mode**: `parallel`  
- **File Path**: `blueprints/script/mfriik/confirmable_notification_multi.yaml`  
- **Source URL**: [https://github.com/mfriik/HA-Confirmable-Notification-for-Multiple-Devices/blob/main/blueprints/script/mfriik/confirmable_notification_multi.yaml](https://github.com/mfriik/HA-Confirmable-Notification-for-Multiple-Devices/blob/main/blueprints/script/mfriik/confirmable_notification_multi.yaml)

---

### 🔗 How to Import

Import directly into Home Assistant via Blueprints ➝ **Import Blueprint** using this URL:

