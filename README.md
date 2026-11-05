# Skill File Checker

A free, private first check for AI skill, rule and instruction files (SKILL.md, AGENTS.md, CLAUDE.md, .cursorrules and set-up guides) before you, or your assistant, follow them in Claude, Cursor, Codex, OpenClaw or similar tools.

Paste a file and the checker lists anything worth a second look, explains each finding in plain English, gives an overall verdict, and ends with the settings that protect you whatever the file says.

**Try it:** https://joopp1.github.io/skill-file-checker/

## Private by design
- One HTML page. Everything runs in your browser.
- Nothing you paste is uploaded, stored or sent anywhere. The page's security policy blocks all network connections, and there are no outside libraries, analytics or tracking.
- Read `index.html` yourself: every rule is listed in plain sight.

## What it looks for

Nearly 60 checks in eight groups, each mapped to the OWASP Agentic Skills Top 10 (AST), the OWASP Top 10 for LLM Applications 2025 (LLM) and the OWASP Top 10 for Agentic Applications (ASI).

| Group | Examples | OWASP |
|---|---|---|
| Takes control of the assistant | instruction overrides, claims that you already agreed, claims of special authority, text addressed to the AI, requests to hide things or report success regardless, pressure never to refuse, attempts to pull out hidden instructions | LLM01, LLM07, ASI01, ASI09, AST01 |
| Removes your safety net | switching off confirmations or the sandbox, administrator rights, reaching outside the project folder, acting on your behalf (sending, posting, paying, pushing), requests for every tool | LLM06, AST03, AST06, ASI02, ASI03 |
| Delivers software or malware | fake "Prerequisites" that ask you to download or paste something (the ClawHavoc pattern, February 2026), program and password-protected archive downloads, switching off antivirus or Gatekeeper, decode-and-run code, pipe-to-shell installs, always pulling the latest version | AST01, AST02, AST07, LLM03, ASI04, ASI05 |
| Can steal your data | private files and wallets (SSH keys, cloud credentials, browser password stores, seed phrases), gathering credentials, sending data to outside addresses, links and images built from your data, real keys pasted into the file | LLM02, LLM05, AST01 |
| Connects to the internet | paste and file-sharing sites, data-collection services, bare IP addresses, link shorteners, disguised addresses, raw file links, instructions loaded from a website at run time, remote-access backdoors | AST02, AST05, AST07, ASI04 |
| Stays after you stop using it | writing to CLAUDE.md, settings, hooks, start-up files and scheduled tasks; writing to the assistant's memory; copying itself into other files or agents; stamping branding into everything you produce | ASI06, ASI07, LLM04, AST09 |
| Can cause damage | mass deletion, wiping drives, force-pushing, dropping databases, clearing logs and history | LLM06, ASI02, AST01 |
| Hides content from you | hidden comments, text styled to be invisible, invisible and direction-changing Unicode, hidden selector characters, look-alike letters, text pushed off-screen, long encoded strings, descriptions that give instructions, unusual YAML in the header, auto-run hooks, imitation names, "official" claims, too-good-to-be-true promises, scripts the check cannot see | LLM01, LLM09, AST01, AST04, AST08 |

It also flags **combinations** that are more serious than their parts: private data plus a way out, a fake prerequisite plus a suspicious source, and switched-off checks plus powerful actions.

## What it cannot do
It reads text and matches patterns. It cannot see scripts a skill downloads later, behaviour that only shows when the skill runs, changes the author makes after you checked, signing and provenance, or new tricks it has no pattern for. OWASP notes that instructions written in ordinary language can slip past any pattern list. A clean result does not mean a file is safe.

Files that document attacks, such as security guides, will trigger findings because they quote the patterns. Read the context.

## For developers
Dedicated scanners go further, for example Snyk's mcp-scan, skilldoctor (command line, CI) and SkillSpector (static plus optional AI analysis).

## About
Built by Joseph Majersky, who writes about AI safety and trust and safety on [LinkedIn](https://www.linkedin.com/in/josephmajersky).

## Licence and support
MIT licence. Provided as is, without warranty. Suggestions for improvement are welcome: please open an issue.
