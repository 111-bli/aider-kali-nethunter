# Setup Aider on Kali NetHunter

This guide is specifically for **Kali NetHunter** on Android devices.

## Important Notes for NetHunter

- NetHunter runs on ARM (usually arm64)
- Use the built-in NetHunter terminal (or Termux if preferred)
- **pipx is strongly recommended** (system pip often causes issues on Android-based setups)
- Resources are limited compared to desktop → keep it lightweight
- Voice/hands-free is more complex on mobile (see notes at bottom)

## 1. Update System & Install Basics

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y git python3 python3-pip python3-venv portaudio19-dev espeak-ng
```

## 2. Install pipx (if not already)

```bash
python3 -m pip install --user pipx
python3 -m pipx ensurepath
```

Restart your terminal or run:
```bash
source ~/.bashrc   # or ~/.zshrc
```

## 3. Install Aider using pipx

```bash
pipx install aider-chat
```

This creates an isolated environment — perfect for NetHunter.

## 4. Verify Installation

```bash
aider --version
```

## 5. Run Aider

```bash
export OPENAI_API_KEY=sk-yourkeyhere   # or use your preferred provider
aider --model gpt-4o   # or claude-3-5-sonnet, etc.
```

## Using with Git Repos

Navigate to your project folder and run `aider` inside it.

## Voice / Hands-Free on NetHunter (Advanced)

Running full voice like on desktop is tricky on mobile because:
- No easy always-on mic in terminal
- Android permissions
- Limited CPU for local STT

**Options:**
- Use Aider's built-in `/voice` mode (type it, speak, Enter)
- For better experience, consider pairing with Termux:API + tasker for wake word (advanced)
- Or just use text mode for now

When you upgrade to a proper PC later, the desktop repo will be much smoother for voice.

## Troubleshooting

- If pipx commands not found: run `pipx ensurepath` again and restart terminal
- Permission issues: make sure you're in the correct NetHunter session with root if needed
- Slow performance: Use smaller/faster models or cloud STT only

## Next Steps

- Clone your projects and start coding with Aider
- For desktop Kali voice automation, see: https://github.com/111-bli/aider-voice-handsfree

Let me know if you hit any errors!