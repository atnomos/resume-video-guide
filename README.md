# 60-Second Resume Video with Claude Code + Remotion  
**Modern motion graphics resume (Disney/Apple vibes) – Step-by-step guide (Feb 2026)**

Tested on MacBook Air (M-series) with Claude Code and Remotion.  
Goal: Create a polished 60-second video resume using AI prompting – no manual coding required.

![Example resume video frame placeholder](https://via.placeholder.com/800x450/0a0a1f/00aaff?text=Your+60s+Resume+Video+Here)  
*(Replace with screenshot of your final MP4 once rendered)*

## Prerequisites
- Mac with Terminal access
- Claude Code already installed & logged in (Pro recommended for longer outputs)
- Internet connection

## 1. Install Homebrew + Node.js (if not already done)

```bash
# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

/# Add to PATH (Apple Silicon)
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"

# Install Node.js
brew install node

# Verify
node -v    # e.g. v22.x or v24.x
npm -v     # e.g. 11.x
npx --version
