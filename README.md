60-Second Resume Video with Claude Code + Remotion
Modern motion graphics resume – Step-by-step guide (Feb 2026)

Tested on MacBook Air (M-series) with Claude Code and Remotion.
Goal: Create a polished 60-second video resume using AI prompting – no manual coding required.
Author: wilfredo (@atnomos) – San Francisco, Ca.

Prerequisites
• Mac with Terminal access
• Claude Code already installed & logged in (Pro recommended for longer outputs)
• Internet connection

1. Install Homebrew + Node.js (skip if already done)

# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Add to PATH (Apple Silicon – most important nuance!)
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"

# Install Node.js
brew install node

# Verify (should show versions – if not, close/reopen Terminal)
node -v    # e.g. v22.x or v24.x
npm -v     # e.g. 11.x
npx --version

Tips:
• Ignore optional npm update notices
• If any command still says “not found” after install → add this line to ~/.zshrc and run source ~/.zshrc:
  export PATH="/opt/homebrew/bin:$PATH"

2. Create Remotion Project

npx create-video@latest

Prompt answers (critical – wrong choice makes Claude struggle):
• Template: Blank
• Add Tailwind CSS?: Yes
• Add agent skills?: Yes
• Scope: Project

Project folder example: my-video

cd my-video
npm install

Common warnings (safe to ignore):
• Deprecated tar / source-map
• Vulnerabilities (transitive deps) → optional cleanup: npm audit fix

3. Increase Claude Code Output Limit (prevents cutoff on complex videos)

export CLAUDE_CODE_MAX_OUTPUT_TOKENS=64000

Verify:
echo $CLAUDE_CODE_MAX_OUTPUT_TOKENS

Make permanent (optional – highly recommended):
Add this line to ~/.zshrc:
export CLAUDE_CODE_MAX_OUTPUT_TOKENS=64000
Then run: source ~/.zshrc

4. Launch Claude Code & Initialize

claude

Inside Claude Code prompt (do this first):
/init

(This creates CLAUDE.md with project context – Claude becomes much more accurate)

5. Paste This Prompt into Claude Code

Using the Remotion skill and best practices (including Tailwind for styling), create a professional 60-second video resume for First Last. It should be modern motion graphics: minimalist, tech-forward, clean kinetic typography, subtle transitions (fades, scales, line reveals), dark navy background with company-inspired blue/teal accents.

Duration: 60 seconds (55-65s ok). 1920x1080, 30fps.

Style: Dark mode (#0a0a1f bg), accents #00aaff/#00d4ff, white/gray text. Sans-serif fonts. Subtle glows/particles on key phrases. Smooth transitions.

Audio: Upbeat motivational instrumental (tech/innovation electronic, sync swells to highlights). Use <Audio src={staticFile("music.mp3")} volume={0.38} loop /> or suggest free Pixabay URL. No voiceover.

Structure with timed scenes:
- 0-10s: Intro – 
- 10-25s: Summary – 
- 25-45s: Experiences – 
- 45-55s: Education & skills – 
- 55-60s: Close –

Tone: Confident, inclusive, innovative—subtle creativity.

First: Detailed scene-by-scene plan with timestamps, text, animation ideas, Tailwind classes.
Then: Generate/update code (src/Composition.tsx, components). Use <Sequence>, spring(), Tailwind.

Iterate based on preview!

6. Preview Live

Open new terminal tab (Cmd+T):
npm run dev

→ Browser opens (localhost:3000 or similar). Refresh page after Claude makes changes.

7. Add Background Music

1. Download free upbeat instrumental MP3
   (Pixabay Audio Library → search "corporate upbeat instrumental")
2. Rename file to music.mp3
3. Drag into project/public/ folder
4. Tell Claude: "Use public/music.mp3 in Audio component with volume 0.4 and loop"

8. Render Final MP4

npx remotion render VideoResume out/resume.mp4 --codec=h264 --audio-codec=aac

Safety checks first:
• Confirm composition ID: npx remotion compositions
   (Usually VideoResume – use the exact name shown)
• Make sure music.mp3 is in public/ (otherwise audio silent)

Output: out/resume.mp4
Play in QuickTime / VLC

9. Common Tweaks (Tell Claude These)

- "Increase name font to 180px and add drop shadow for readability"
- "Shorten summary to 12s, stagger bullets more dramatically"
- "Lower music volume to 0.3 + add 1s fade-in"
- "Add subtle sparkle/glow on company mentions"
- "Make skills tags larger (text-5xl) and space them out"
- "Use brighter teal accents (#00cfff) for better contrast"

Result
A standout LinkedIn / portfolio video highlighting your experience.
Upload out/resume.mp4 and share!

Made with ❤️ using Claude Code + Remotion (Feb 2026)
