# XIAO ESP32S3 + AI-Assisted Embedded Programming

## Student Self-Study Guide

**For Fab Academy Embedded Programming Week**
**Prepared by: Feng Lei, Seeed Studio / Chaihuo Makerspace**
**Date: July 2025**

---

## 📋 Overview

This guide walks you through using AI (Large Language Models) to program the XIAO ESP32S3 development board. You'll experience two approaches:

| Path | Description | Difficulty | Time |
|------|-------------|------------|------|
| **Path 1: AI-Assisted** | You drive, AI helps write code | ⭐ Beginner | 15 min |
| **Path 2: AI Agent** | AI drives the entire workflow | ⭐⭐ Advanced | 15 min |

**No prior programming experience required for Path 1!**

---

## 🔗 Important Links

| Resource | Link |
|----------|------|
| XIAO ESP32S3 Wiki | https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/ |
| Arduino IDE Download | https://www.arduino.cc/en/software |
| SenseCraft AI | https://sensecraft.seeed.cc/ai/home |

### AI Platforms (use any one)

- **Claude**: https://claude.ai
- **ChatGPT**: https://chat.openai.com
- **Gemini**: https://gemini.google.com
- **Grok**: https://grok.com
- **DeepSeek**: https://chat.deepseek.com

---

## 🔧 Hardware: XIAO ESP32S3

The XIAO ESP32S3 is a tiny but powerful development board from Seeed Studio.

**Key Features:**
- ESP32-S3 dual-core processor
- Built-in LED (GPIO21)
- WiFi & Bluetooth
- Camera connector (OV2640)
- USB-C for programming
- Ultra-small size (21x17.8mm)

**What you need for this guide:**
- 1× XIAO ESP32S3
- 1× USB-C cable
- A computer with Arduino IDE installed

---

## 🛠️ Setup: Arduino IDE for XIAO ESP32S3

If you haven't set up Arduino IDE for XIAO yet, follow these steps:

### Step 1: Install Arduino IDE

Download from https://www.arduino.cc/en/software

### Step 2: Add ESP32 Board Support

1. Open Arduino IDE
2. Go to **File → Preferences**
3. In "Additional Boards Manager URLs", add:

```
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
```

4. Click OK

### Step 3: Install the Board Package

1. Go to **Tools → Board → Boards Manager**
2. Search for **"esp32"**
3. Install **"esp32 by Espressif Systems"**

### Step 4: Select Board and Port

1. **Tools → Board → esp32 → XIAO_ESP32S3**
2. **Tools → Port → Select your XIAO's serial port**

### Step 5: Test with Blink

1. **File → Examples → 01.Basics → Blink**
2. Click Upload (→ button)
3. The built-in LED should start blinking

> **Tip:** If upload fails, hold the BOOT button while connecting USB, then try again.

---

## 🎯 Path 1: AI-Assisted Programming

### Concept

You are the driver. AI is your co-pilot.

You describe what you want in natural language → AI generates Arduino code → You copy it to Arduino IDE → Upload to XIAO → See results.

### 🏆 5 Golden Rules

To get the best results from AI, follow these rules:

| # | Rule | What to Do |
|---|------|------------|
| 1 | **Be Specific** | Describe exact behavior, timing, and interactions |
| 2 | **Give Context** | Tell AI your board model, IDE, and libraries |
| 3 | **Share References** | Include documentation links and function names |
| 4 | **Use Visuals** | Upload pinout diagrams or describe expected output |
| 5 | **Build Step by Step** | Start simple, add features one at a time |

### 🚩 Challenge 1: Blink with AI

Copy this prompt into your AI chat:

```
I have a Seeed Studio XIAO ESP32S3 development board.
I'm using Arduino IDE.

Please write an Arduino program that:
- Makes the built-in LED (GPIO21) blink every 1 second
- Prints "LED ON" and "LED OFF" to Serial Monitor

Keep the code simple with clear comments.
```

**What to do:**
1. Paste the prompt into your AI tool
2. Copy the generated code into Arduino IDE
3. Upload to XIAO ESP32S3
4. Open Serial Monitor (magnifying glass icon, set baud rate to 115200)
5. Observe the LED blinking and serial output

### 🚩 Challenge 2: Button-Controlled LED

Now let's add interaction. Ask AI:

```
I have a Seeed Studio XIAO ESP32S3 in Arduino IDE.

Modify the blink program so that:
- When the device starts, LED blinks every 1 second (default mode)
- I'll connect a button between GPIO2 and GND (using internal pull-up)
- Each button press cycles through 3 modes:
  1. Slow blink (1 second interval)
  2. Fast blink (200ms interval)  
  3. LED always on
- Press again to return to mode 1

Requirements:
- Use millis() instead of delay() so the program stays responsive
- Add button debouncing (at least 200ms)
- Print the current mode to Serial Monitor
```

> **No button?** No problem! Ask AI to use the BOOT button (GPIO0) instead, or just use Serial Monitor commands to switch modes.

### 🚩 Challenge 3: WiFi Scanner

Try something more advanced:

```
I have a Seeed Studio XIAO ESP32S3 in Arduino IDE.

Write a program that:
- Scans for nearby WiFi networks
- Prints the network name (SSID) and signal strength (RSSI) to Serial Monitor
- Sorts results by signal strength (strongest first)
- Rescans every 10 seconds
- Turns LED on during scanning, off when idle
```

### 🚩 Challenge 4: Create Your Own!

Think of something you want to build and describe it to AI. Ideas:

- A temperature logger (if you have a sensor)
- A Morse code transmitter using the LED
- A reaction time game using button and LED
- A WiFi signal strength meter

**Remember the 5 Golden Rules!**

---

## 🤖 Path 2: AI Agent (Advanced)

### Concept

In Path 1, you manually copy code between AI chat and Arduino IDE. An AI Agent eliminates this back-and-forth — it directly controls your terminal, writes files, compiles code, uploads to hardware, reads errors, and fixes them. All you do is describe the goal.

### What Changes?

| Path 1: AI-Assisted | Path 2: AI Agent |
|----------------------|------------------|
| You copy-paste code between AI and IDE | AI writes files and runs commands directly |
| You read errors and report them to AI | AI reads errors and fixes them itself |
| You click "Upload" in Arduino IDE | AI calls `arduino-cli` to compile and upload |
| Multiple rounds of manual effort | One description → AI handles the rest |

### Tools You Can Try

| Tool | Description | Free? |
|------|-------------|-------|
| **Claude Code** | Anthropic's CLI coding agent | Free tier available |
| **Cursor** | AI-powered code editor | Free tier available |
| **GitHub Copilot** | AI pair programming in VS Code | Free for students |
| **Codex CLI** | OpenAI's terminal agent | Requires API key |

### Step-by-Step: How to Use an AI Agent

The typical workflow follows a simple pattern: **create a project folder → write a context document → let AI take over.**

#### Step 1: Create a Project Folder

Create a new folder on your computer for this project:

```bash
mkdir ~/xiao-blink
cd ~/xiao-blink
```

#### Step 2: Write a Context & Requirements Document

Create a Markdown file (e.g., `RULES.md`) inside the folder. This document tells the AI Agent everything it needs to know — your hardware, environment, goals, and constraints.

This is the most important step. A well-written context document is the difference between success and failure.

**Create `RULES.md` with content like this:**

```markdown
# Project: XIAO ESP32S3 LED Blink

## Hardware
- Board: Seeed Studio XIAO ESP32S3
- Built-in LED: GPIO21
- Connection: USB-C to computer
- Reference: https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/

## Environment
- OS: [macOS / Windows / Linux] ← fill in yours
- Framework: Arduino
- Tool: arduino-cli (install if not present)
- Board FQBN: esp32:esp32:XIAO_ESP32S3

## Requirements
Make the built-in LED blink every 1 second.
Print "LED ON" and "LED OFF" to Serial at 115200 baud.

## Rules
- You have full control of the terminal. Do not ask me to run commands.
- Automate everything: environment setup, code writing, compiling, uploading.
- If compilation or upload fails, read the error and fix it yourself.
- After success, briefly document what you did in a README.md.
```

> **Why a file instead of just chatting?** Because the agent can re-read this file anytime during development. It serves as persistent context that doesn't get lost in conversation history.

#### Step 3: Launch the AI Agent

Open your AI coding tool in the project folder and point it to your context document.

**Example with Claude Code:**

```bash
cd ~/xiao-blink
claude
# Then tell it: "Read RULES.md and complete the project according to the requirements."
```

**Example with Cursor:**

1. Open the `~/xiao-blink` folder in Cursor
2. Open the AI chat panel
3. Type: "Read RULES.md and complete the project. Set up the environment, write the code, compile, and upload to my XIAO ESP32S3."

**Example with Codex CLI:**

```bash
cd ~/xiao-blink
codex "Read RULES.md and complete all tasks described in it."
```

#### Step 4: Watch AI Work

Once started, the agent will typically:

1. **Read** your `RULES.md` to understand the project
2. **Check/install** arduino-cli if needed
3. **Install** the ESP32 board core
4. **Create** the Arduino sketch (`.ino` file)
5. **Detect** the serial port of your XIAO
6. **Compile** the code
7. **Upload** to the board
8. **Verify** the result — if errors occur, it reads them and tries again
9. **Document** what it did in a README

Your role during this process:
- **Watch** and learn how AI approaches the problem
- **Approve** any actions if the tool asks for confirmation
- **Help** if the agent can't detect the serial port (you may need to tell it which port)
- **Intervene** only if it gets stuck in a loop

#### Step 5: Try a More Complex Project

Once Blink works, create a new `RULES.md` with a harder challenge:

```markdown
# Project: XIAO ESP32S3 WiFi Scanner

## Hardware
- Board: Seeed Studio XIAO ESP32S3
- Built-in LED: GPIO21
- Connection: USB-C to computer
- Reference: https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/

## Environment
- OS: [your OS]
- Framework: Arduino
- Tool: arduino-cli
- Board FQBN: esp32:esp32:XIAO_ESP32S3

## Requirements
1. Scan nearby WiFi networks every 10 seconds
2. Print SSID and signal strength (RSSI) to Serial Monitor
3. Sort by signal strength (strongest first)
4. LED on during scanning, off when idle

## Rules
- Fully automated: do not ask me questions
- Handle all errors autonomously
- Document the process in README.md
```

### Tips for Success

- **Be detailed in RULES.md** — the more context you give, the better the result
- **Include reference links** — AI agents can often fetch documentation from URLs
- **Start with simple projects** — Blink first, then WiFi, then sensors
- **Don't worry about failures** — AI agent workflows don't succeed 100% of the time, and that's completely normal. The goal is to experience the process and see the possibilities
- **Save your RULES.md files** — they become reusable templates for future projects

---

## 🌟 Bonus: SenseCraft AI — No-Code Vision

Want to see XIAO ESP32S3 do something truly impressive with zero code?

**SenseCraft AI** turns your XIAO ESP32S3 (with OV2640 camera) into an AI vision sensor — no programming required.

### How to Try

1. Visit https://sensecraft.seeed.cc/ai/home
2. Connect your XIAO ESP32S3 (with camera module) via USB
3. Flash the SenseCraft firmware through the web interface
4. Choose a vision model (object detection, face detection, etc.)
5. See AI vision running on your tiny board!

> **Requirement:** You need the XIAO ESP32S3 **Sense** version (with camera connector) and an OV2640 camera module.

---

## ❓ Troubleshooting

### Common Issues

| Problem | Solution |
|---------|----------|
| Upload fails | Hold BOOT button while connecting USB, then upload |
| Port not found | Install USB driver; try different USB cable |
| Code won't compile | Copy the full error message and paste it to AI — ask it to fix |
| LED doesn't blink | Check if you selected the correct board (XIAO_ESP32S3) |
| AI gives wrong pin numbers | Always remind AI: "Built-in LED is on GPIO21 for XIAO ESP32S3" |

### The Most Important Debugging Tip

**When you get an error, copy the ENTIRE error message and paste it to AI.** Ask:

```
I got this error when compiling/uploading to XIAO ESP32S3 in Arduino IDE:

[paste error message here]

Please help me fix it.
```

AI is excellent at reading error messages and suggesting fixes.

---

## 💡 Key Takeaways

1. **AI dramatically lowers the barrier** to hardware programming — you don't need to memorize syntax
2. **Be specific** when talking to AI — the better your description, the better the code
3. **Iterate** — start simple, test, then add features one at a time
4. **Errors are normal** — just feed them back to AI for solutions
5. **Your creativity is the limit**, not your programming skills

---

## 📚 Further Resources

- Full Workshop Materials (Open Source): https://drive.google.com/drive/folders/1qB1LxrVsOYDFkEY-KHx9GVcmIzn0ymNr
- XIAO ESP32S3 Wiki: https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/
- Seeed Studio Interactive Signage Contest 2025: https://www.seeedstudio.com/interactive-signage-contest-2025
- Seeed Studio Discord: Join for community support

---

*With AI assistance, you're only limited by imagination, not programming skills!*

*Contact: For technical support or collaboration, feel free to reach out to Seeed Studio / Chaihuo Makerspace.*
