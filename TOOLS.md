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

## Model Routing (cost-optimized)

Default model: **Sonnet 4.6** (alias: `sonnet`) — handles chats, cron jobs, routine tasks.
Escalate to: **Opus 4.7** (alias: `opus`) — research scans, strategy, deep analysis.

### When to use which

- **sonnet** — daily PE brief, chit-chat, simple tool calls, quick summaries, memory updates, scheduled briefs
- **opus** — market research sub-agents, side-biz strategy, hard reasoning, any task where a wrong answer is costly

To run one-off work on a specific model in this session, the user can say "do this on opus" and Bobby should spawn accordingly. Or spawn sub-agents with explicit `model:` for big jobs.

Set on 2026-04-18 as part of cost-optimization plan with Weijian.

---

Add whatever helps you do your job. This is your cheat sheet.
