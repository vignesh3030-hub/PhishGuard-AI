# PhishGuard AI — Browser Extension

Explainable, real-time phishing / cloned-webpage detection for Chrome, Edge, Brave, Arc, Opera (MV3) and Firefox (115+).

## What it does
Before you type a password, OTP or card number, PhishGuard analyses the page with nine engines:
URL, domain, identity, DOM, form, redirect, visual-similarity, brand registry and risk scoring.
Verdicts: SAFE · LOW RISK · SUSPICIOUS · HIGH RISK · PHISHING · LOCAL/UNKNOWN — always with a reason list.

## Install (unpacked)
1. Download and unzip `phishguard-ai-extension.zip`.
2. Open `chrome://extensions` (or `edge://extensions`).
3. Enable **Developer mode**.
4. Click **Load unpacked** and select the unzipped folder.
Firefox: `about:debugging` → This Firefox → Load Temporary Add-on → pick `manifest.json`.

## Build from source
```
bun build extension/src/content.ts   --outfile extension/content.js    --target browser --minify
bun build extension/src/background.ts --outfile extension/background.js --target browser --format esm --minify
bun build extension/src/popup.ts      --outfile extension/popup.js      --target browser --format esm --minify
```
Engine tests: `bunx vitest run src/lib/phishguard`

## Privacy
Scoring runs entirely in the browser. Field *values* are never read — only structure
(types, names, form actions). No passwords, OTPs, card numbers or tokens are stored or transmitted.

## Detection rule
HTTP, localhost, IP hosts and dev ports are risk *indicators*, never proof. Only their combination
with brand impersonation, credential forms, cross-domain submission and UI cloning raises a phishing verdict.
