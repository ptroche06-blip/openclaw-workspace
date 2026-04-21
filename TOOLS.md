# TOOLS.md - Local Notes

Skills define _how_ tools work. This file is for _your_ specifics — the stuff that's unique to your setup.

## What Goes Here

Things like:

- Camera names and locations
- SSH hosts and aliases
- Preferred voices for TTS
- Speaker/room names
- Device nicknames
- Anything environment-specific

## Examples

```markdown
### Gmail / Calendar (Google Workspace)

- Account: ptroche06@gmail.com
- CLI: gog (installed at /opt/homebrew/bin/gog)
- Auth file: ~/.openclaw/workspace/.gog_credentials.json (do not share)
- Connected services: gmail, calendar, drive, contacts, docs, sheets

**Common commands:**
- `GOG_ACCOUNT=ptroche06@gmail.com gog gmail search 'in:inbox' --max 10`
- `GOG_ACCOUNT=ptroche06@gmail.com gog calendar events ptroche06@gmail.com --from 2026-04-19 --to 2026-04-25`
- Set `GOG_ACCOUNT=ptroche06@gmail.com` to avoid repeating --account flag

### Cameras

- living-room → Main area, 180° wide angle
- front-door → Entrance, motion-triggered

### SSH

- home-server → 192.168.1.100, user: admin

### TTS

- Preferred voice: "Nova" (warm, slightly British)
- Default speaker: Kitchen HomePod
```

## Why Separate?

Skills are shared. Your setup is yours. Keeping them apart means you can update skills without losing your notes, and share skills without leaking your infrastructure.

---

Add whatever helps you do your job. This is your cheat sheet.
