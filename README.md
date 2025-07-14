# Home Assistant Blueprint: Multi-Press Button Actions

This blueprint allows you to assign different actions to a **single button** entity, based on the type of press:
- **Single press**
- **Double press**
- **Long press**

It is especially useful for button devices that report the type of press in their `event_type` attribute (e.g., Zigbee buttons, Matter buttons, etc.).

---

## ✅ Features

- Responds to `single_press`, `double_press`, and `long_press`
- Compatible with entities in the `event.*` domain
- Easy to reuse — just plug in your entity and actions in the UI
- Clean logic structure using `choose:` block for multi-action handling

---

## 🧰 Requirements

- Aqara Wireless Mini Switch
- Home Assistant 2023.6 or newer is recommended (for full UI selector support)

---

## 🚀 How to Use

1. Copy the YAML file to your Home Assistant config:
