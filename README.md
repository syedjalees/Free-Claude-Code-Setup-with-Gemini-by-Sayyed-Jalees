

# 🚀 Free Claude Code Setup With Google Gemini

A complete & beginner-friendly guide to install, configure, and run **Claude Code + Gemini API Router** on Windows.

---
**Just Follow the Steps**

## ✅ Step 1 — Generate FREE Google Gemini API Key

1. Go to **Google AI Studio** → [https://aistudio.google.com](https://aistudio.google.com)
2. Click on **“Get API Key”**
3. Click **“Create API Key”**
4. Name your Key & Project
5. Create the Key
6. Save it for configuration
7. For now move to Step 2

---

## ✅ Step 2 — Install Claude Code + Routing Modules

Open **PowerShell as Administrator**, then:

* Check Node version:

```sh
node -v
```

Version **20 or above** → ✔ OK

If error or older version → download latest Node: [https://nodejs.org](https://nodejs.org)

Now install Claude Code + Router:

```sh
npm install -g @anthropic-ai/claude-code @musistudio/claude-code-router
```

---

## ✅ Step 3 — Create Required Folders

Run these commands in PowerShell:

```sh
mkdir $HOME/.claude-code-router
mkdir $HOME/.claude
```

---

## ✅ Step 4 — Create `config.json`

> ⚠ **The EOF commands only works in Linux and Mac Shells doesn't work in Windows, that is why using Notepad is recommended** → use Notepad.

Just Run this command to make notepad
```sh
notepad $HOME/.claude-code-router/config.json
```

Paste the following JSON, and **replace `$GOOGLE_API_KEY` with your actual API key**:

```json
{
  "LOG": true,
  "LOG_LEVEL": "info",
  "HOST": "127.0.0.1",
  "PORT": 3456,
  "API_TIMEOUT_MS": 600000,
  "Providers": [
    {
      "name": "gemini",
      "api_base_url": "https://generativelanguage.googleapis.com/v1beta/models/",
      "api_key": "$GOOGLE_API_KEY",
      "models": [
        "gemini-2.5-flash",
        "gemini-2.0-flash"
      ],
      "transformer": {
        "use": ["gemini"]
      }
    }
  ],
  "Router": {
    "default": "gemini,gemini-2.5-flash",
    "background": "gemini,gemini-2.5-flash",
    "think": "gemini,gemini-2.5-flash",
    "longContext": "gemini,gemini-2.5-flash",
    "longContextThreshold": 60000
  }
}
```

✅Save → Close Notepad.

---

## ✅ Step 5 — Set Your Gemini API Key as Environment Variable

Run this command with **your actual API key**:

```sh
[System.Environment]::SetEnvironmentVariable('GOOGLE_API_KEY', 'YOUR_API_KEY_HERE', 'User')
```

Example:

```sh
[System.Environment]::SetEnvironmentVariable('GOOGLE_API_KEY', 'AIzaSy.............', 'User')
```

Close PowerShell → reopen it.

Verify:

```sh
echo $env:GOOGLE_API_KEY
```

If it shows your key → ✔ Continue.

---

## ✅ Step 6 — Verify Installation

Run one-by-one:

```sh
claude --version
ccr version
echo $env:GOOGLE_API_KEY
```

If everything responds → ✔ Good to go.

---

## ✅ Step 7 — Daily Workflow (How to Use It)

### **Window 1 — Start Router Server**

```sh
ccr start
```

If you see:

```
⚠️ API key is not set. HOST is forced to 127.0.0.1.
Loaded JSON config from: C:\Users\Admin\.claude-code-router\config.json
```

This means everything is working fine.

**Keep this window open.**

---

### **Window 2 — Start Claude Code**

Go to your project folder:

```sh
cd your-project-folder
```

Start AI coding environment:

```sh
ccr code
```

---

## ✅ Step 8 — Test the AI

Inside the prompt box type:

```
hi
```

If it replies →
🎉 **Congratulations! You have successfully set up Claude Code with your Gemini API key!**

Best of luck for your **Hackathon!** 🏆

---

---

#  Made with 💝 by SAYYED JALEES

<p align="center">
  <a href="https://github.com/syedjalees" target="_blank">
    <img src="https://img.shields.io/badge/Made%20by-SAYYED%20JALEES-blue?style=for-the-badge&logo=github" />
  </a>
</p>

---


