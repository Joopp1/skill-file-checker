# Skill File Checker

A free, private first check for AI skill, rule and instruction files (SKILL.md, AGENTS.md, CLAUDE.md, .cursorrules) before you use them with Claude, Cursor, Codex or similar tools.

Paste a file, and the checker lists anything worth a second look, explains each finding in plain English, and ends with the settings that protect you whatever the file says.

## Private by design
- One HTML page. Everything runs in your browser.
- Nothing you paste is uploaded, stored or sent anywhere. The page's security policy blocks all network connections, and there are no outside libraries, analytics or tracking.
- Read `index.html` yourself: the rules are listed in plain sight near the bottom.

## What it looks for
Instruction overrides, text addressed to the AI, claims of special authority, requests to hide things from you, removal of confirmation steps, internet access and webhooks, software installs, passwords and private keys, changes to settings that persist (CLAUDE.md, memory, start-up hooks), pressure never to refuse, hidden comments, long encoded text, invisible characters, and requests for every tool or for powerful tools.

## What it cannot do
It reads text and matches patterns. It cannot see scripts a skill downloads later, behaviour that only shows when the skill runs, or new tricks it has no pattern for. A clean result does not mean a file is safe.

## For developers
Dedicated scanners go further, for example skilldoctor (command line, CI) and SkillSpector (static plus optional AI analysis).

## About
Built by Joseph Majersky, who writes about AI safety and trust and safety on [LinkedIn](https://www.linkedin.com/in/josephmajersky).

## Licence and support
MIT licence. Provided as is, without warranty. Suggestions for improvement are welcome: please open an issue.
