# Ganchi — API key handoff (for Pablo)

_The key itself is in your Telegram DM from Seth. Do not paste it back into the group._

## What this key is

An Anthropic API key scoped to a dedicated `ganchi` workspace in Spirit's Anthropic Console. It powers ganchi-the-agent on your mac mini — Claude Code sessions, agent runtime, anything that needs to talk to Claude.

Spend lives inside this workspace only; it cannot touch other Spirit / Solienne usage.

## Install on the mac mini

1. Create a config directory ganchi can read:

   ```bash
   mkdir -p ~/.config/ganchi
   chmod 700 ~/.config/ganchi
   ```

2. Save the key into an env file (paste the key Seth sent you in place of `PASTE_KEY_HERE`):

   ```bash
   cat > ~/.config/ganchi/.env <<EOF
   ANTHROPIC_API_KEY=PASTE_KEY_HERE
   EOF
   chmod 600 ~/.config/ganchi/.env
   ```

3. For Claude Code on the mac mini, export it in your shell rc (`~/.zshrc` or `~/.bashrc`):

   ```bash
   echo 'export $(grep ANTHROPIC_API_KEY ~/.config/ganchi/.env)' >> ~/.zshrc
   source ~/.zshrc
   ```

   Then `claude` should pick it up. Verify with `claude --version` and a small test prompt — if you see auth errors, the key didn't load.

4. For the ganchi runtime (when it exists — Telegram bot, NFC landing page replies, etc.), point it at the same file. Same key, different consumers.

## Rules

- **Do not commit.** Add `.env` and `.config/ganchi/` to `.gitignore` if you're in any repo that touches them.
- **Do not paste in Telegram or other group chats** — Seth's DM was the one-time delivery channel.
- **Do not share with anyone else on the team without telling Seth first** — Fran, Vlad, Samer, and Josh all have their own access patterns and don't need this key.
- **If your mac mini is ever physically lost or compromised**, tell Seth immediately — we'll rotate same-day.

## Spend

- The workspace has a spend cap set on Seth's side. You won't be able to overspend by accident.
- If ganchi starts burning unexpectedly (suddenly $50+ a day during dev), pause and ping Seth — usually means a loop somewhere.

## Rotation

This key rotates on **2026-06-08** (day after NFC Summit closes). Seth will send a new one via 1Password share link. Old key gets revoked the same day.

## Questions go to Seth in DM, not the group.
