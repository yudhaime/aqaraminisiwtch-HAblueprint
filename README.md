# Home Assistant Blueprint: Aqara Mini Switch Multi-Press

[![Import Blueprint](https://my.home-assistant.io/badges/automation_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?url=https://raw.githubusercontent.com/yudhaime/aqaraminisiwtch-HAblueprint/main/miniswitch/aqaraminiswitch.yaml)


This blueprint allows you to assign different actions to a **single button** entity, based on the type of press:
- **Single press**
- **Double press**
- **Long press**

It is especially useful for Zigbee/Matter button devices that report the type of press in their `event_type` attribute (not as device triggers).

---

## ✅ Features

- Responds to `single_press`, `double_press`, and `long_press`
- Works with entities in the `event.*` domain
- Reusable for different buttons and actions
- Simple choose-based action structure

---

## 🧰 Requirements

- A button entity (typically `event.your_button`) that updates its `event_type` attribute when pressed
- Home Assistant 2023.6+ is recommended for full selector support

---

## 🚀 How to Use

1. Click the “Import Blueprint” button above ☝️  
   Or manually copy the YAML to:
    /config/blueprints/automation/aqaraminiswitch/button_multi_press.yaml
2. Reload Blueprints or restart Home Assistant

3. Go to:
**Settings → Automations & Scenes → + Create Automation → Use Blueprint**

4. Select **"Multi-Press Button Actions"**

5. Choose your button entity and assign actions for:
- Single press
- Double press
- Long press

---

## 🔧 Blueprint Inputs

| Input                 | Description                                          |
|----------------------|------------------------------------------------------|
| `button_event`         | The button entity (from `event.*` domain)          |
| `single_press_action` | Action to run when the button is single-pressed     |
| `double_press_action` | Action to run when the button is double-pressed     |
| `long_press_action`   | Action to run when the button is long-pressed       |

---

## ⚠️ Why Did My Button Actions (Single/Double/Long) Disappear?

In older versions of Home Assistant, many button devices showed pre-defined actions (single/double/long press) in the **device automation UI**.  
Recently, you may notice:
- Those actions no longer appear under Device → Automations
- You only see a generic `pressed` option — or nothing at all

This happens because:
- Home Assistant core now prefers **standard device triggers**
- Many button devices only expose a generic `event` entity
- Press type like `single_press` is now stored in **attributes**, not as device triggers

---

## ✅ Solution

This blueprint restores that missing functionality by:
- Listening for **any state change** in the event entity
- Checking the `event_type` attribute
- Running the correct action based on that value

---

## 🧪 Test If Your Button Works

1. Open **Developer Tools → States**
2. Find your button entity (e.g., `event.aqara_button`)
3. Press the physical button
4. Check if `event_type` updates to:
- `single_press`
- `double_press`
- `long_press`

If so, you're good to go ✅

---

## 🪪 License

MIT License
