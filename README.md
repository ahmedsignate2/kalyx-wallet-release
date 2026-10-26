# Kalyx Wallet — Releases

**Official Android releases (signed APK) of Kalyx Wallet, a non-custodial multi-chain crypto wallet.**
Source code: **[github.com/ahmedsignate2/kalyx-wallet](https://github.com/ahmedsignate2/kalyx-wallet)** · Site: **[kalyxwallet.com](https://kalyxwallet.com)** · Web dashboard: **[app.kalyxwallet.com](https://app.kalyxwallet.com)** · Security: **[vulnerability disclosure program](https://github.com/ahmedsignate2/kalyx-wallet/blob/main/docs/security/VDP.md)**

![Non-custodial](https://img.shields.io/badge/keys-non--custodial-2ea44f)
![No independent audit](https://img.shields.io/badge/security%20audit-none%20yet-orange)
![Android](https://img.shields.io/badge/platform-Android%20APK-3ddc84)
[![Latest release](https://img.shields.io/github/v/release/ahmedsignate2/kalyx-wallet-release?label=latest)](https://github.com/ahmedsignate2/kalyx-wallet-release/releases/latest)
[![Vulnerability disclosure: HackerOne](https://img.shields.io/badge/VDP-HackerOne-494649)](https://github.com/ahmedsignate2/kalyx-wallet/blob/main/docs/security/VDP.md)

> 🚀 **Open beta — free. Try it and tell us what you think:** Telegram [@kalyxntw](https://t.me/kalyxntw) · support@kalyxwallet.com
> 🚀 **Bêta ouverte — gratuite. Testez-la et donnez votre avis.**
>
> ⚠️ **Beta software — not independently audited. Only use funds you can afford to lose.**
> ⚠️ **Version bêta — non auditée. N'utilisez que des montants que vous pouvez vous permettre de perdre.**

---

## 📥 Download / Télécharger

👉 **[kalyx-wallet.apk — latest version](https://github.com/ahmedsignate2/kalyx-wallet-release/releases/latest/download/kalyx-wallet.apk)**

- Neutral link that always points to the latest version: **[kalyxwallet.com/download](https://kalyxwallet.com/download)**
- All versions: [Releases](https://github.com/ahmedsignate2/kalyx-wallet-release/releases)
- Checksum of the latest APK: **[kalyx-wallet.apk.sha256](https://github.com/ahmedsignate2/kalyx-wallet-release/releases/latest/download/kalyx-wallet.apk.sha256)**

**Only download Kalyx from this repository or from kalyxwallet.com.** Any APK obtained elsewhere (Telegram groups, third-party stores, "mods") must be considered malicious.

### Installation (Android)
1. Download the APK on your phone and open it.
2. If Android asks, allow installation from this source (*Settings → Security → Install unknown apps*).
3. Open Kalyx, create a wallet (or import a recovery phrase) and **write your 12 words down offline**.

**Updating:** download the new APK and install it over the existing app — your wallets are kept (same signing key). There are **no over-the-air updates** in release builds: the app only runs the code of the APK you installed.

### Other platforms / Autres plateformes

| | |
|---|---|
| 🧩 **Browser extension (beta)** | Chrome, Edge, Brave — invite-only beta on the Chrome Web Store. Full wallet (keys encrypted on the computer) or **companion mode** (keys stay on your phone, every signature approved in the app). EVM, Solana, Bitcoin, TON. |
| 🖥️ **Web dashboard** | [app.kalyxwallet.com](https://app.kalyxwallet.com) — the same interface as the extension, linked to your phone by QR code (WalletConnect): no key, no password. |
| ✈️ **Telegram** | Mini app (the web dashboard) + bot: prices, gas, token scans, price alerts. |
| 🍎 **iOS** | Coming later. |

---

## ✅ Verify the APK / Vérifier l'APK

Every release publishes the APK **and** its `kalyx-wallet.apk.sha256`. The SHA-256 is also printed in the release notes.

**1. Checksum** — the downloaded file is exactly the published one:
```bash
sha256sum -c kalyx-wallet.apk.sha256
# kalyx-wallet.apk: OK
```
(Windows PowerShell: `Get-FileHash kalyx-wallet.apk -Algorithm SHA256`)

**2. Signature** — the APK was signed with the official Kalyx key. The signing certificate fingerprint is the same for all official releases; Android refuses to update an app with a different key:
```bash
apksigner verify --print-certs kalyx-wallet.apk
```
Expected certificate SHA-256:
```
DD:CE:CC:7F:5B:1A:08:C3:4C:32:07:2B:39:04:2C:27:8F:2F:70:1F:2E:52:DE:F2:87:4D:9E:8D:C2:A8:8A:F0
```
(`apksigner` ships with the Android SDK build-tools.)

If either check fails, **do not install** and report it (see Security).

---

## ✨ What the app does / Ce que fait l'application

- **65 networks** — 62 EVM networks (Ethereum, Base, Arbitrum, Optimism, Polygon, BNB Chain, Avalanche…) plus **Bitcoin** (native SegWit), **Solana** and **TON**, aggregated in one balance. Test networks (Sepolia, Base Sepolia, Monad Testnet, Solana Devnet, TON Testnet) can be shown, kept apart and never counted in your total.
- **Send in four steps** — asset, recipient, amount, then **hold to send**. **Blocking** address-poisoning detection, first-time-recipient warning, **Anti-Drainer** transaction simulation.
- **Every signature explained** — plain-language summary and a **risk score** (0-100, same engine in the app and the extension); a high score requires holding to sign.
- **Anti-coercion** — a **duress code** opens a decoy wallet: your real wallets, contacts and history stay invisible. A **whitelist** keeps sends to approved addresses only (changes take effect after 24 h).
- **Swap & bridge** — LI.FI and Relay (EVM, cross-chain), Jupiter (Solana), STON.fi (TON). Kalyx fee: 0.3 % on swaps, 0 % on send/receive and Earn.
- **Earn** — Aave v3, Lido, Rocket Pool, Benqi, Jito, Marinade, Tonstakers. 0 % Kalyx fee.
- **dApps** — built-in browser, **WalletConnect v2** (EVM, Solana, Bitcoin) and **TON Connect**. Spending approvals can be reviewed and **revoked in bulk**.
- **Connection tracking** — for every linked site or extension: its last real sign of life (green dot only if it answers), its expiry date, and an immediate disconnect.
- **Companion mode** — link the browser extension or the web dashboard to your phone with one QR code: all your wallets and accounts, keys never leave the phone.
- **Security** — AES-256-GCM with a key derived from your PIN (scrypt), Keystore storage, biometrics, growing delay after a wrong PIN (clock changes don't shorten it), auto-lock, blur in recent apps.
- **Encrypted backup** — local file or private Google Drive folder, encrypted on-device with your password. Useless without it, even to Kalyx.
- **Copilot** — optional assistant with your own AI key (BYOK: DeepSeek, OpenAI, Anthropic, Gemini, Groq, OpenRouter…). Off by default; it never sees your keys, phrase or PIN.
- **Watch-only wallets**, account discovery on import, contacts, price alerts, **15 languages**.

---

## 🔒 Security / Sécurité

- **Non-custodial**: keys are generated and stay on your device. No Kalyx server, no account, no access to your funds.
- **No independent audit yet.** Built and maintained by a solo developer.
- Kalyx will **never** ask for your recovery phrase, private key, PIN or password — not in the app, not by e-mail, not on Telegram.

### Report a vulnerability / Signaler une faille

Kalyx runs a **vulnerability disclosure program (VDP) on HackerOne**, without monetary rewards: valid reports are credited publicly (with your consent) in the release notes.

- Policy, rules of engagement and safe harbor: **[VDP.md](https://github.com/ahmedsignate2/kalyx-wallet/blob/main/docs/security/VDP.md)**
- Assets in scope and out of scope: **[SCOPE.md](https://github.com/ahmedsignate2/kalyx-wallet/blob/main/docs/security/SCOPE.md)** — only the **latest release** of the APK is in scope.
- How to report: **[SECURITY.md](https://github.com/ahmedsignate2/kalyx-wallet/blob/main/SECURITY.md)** — through the HackerOne program, or support@kalyxwallet.com with "SECURITY" in the subject. **Never in public issues.**

Terms & privacy: [kalyxwallet.com/terms](https://kalyxwallet.com/terms/) · [kalyxwallet.com/privacy](https://kalyxwallet.com/privacy/)

---

## 🧪 Report a bug / Signaler un bug

- Open an **[issue](https://github.com/ahmedsignate2/kalyx-wallet-release/issues)** (app version, phone, steps, screenshot) — not for security issues.
- From the app: *Menu → Support* generates a diagnostic ticket **with no sensitive data**.
- E-mail: **support@kalyxwallet.com**

---

## 💼 Licensing & acquisition

Kalyx source code is proprietary and available for review at [kalyx-wallet](https://github.com/ahmedsignate2/kalyx-wallet) (see its [LICENSE](https://github.com/ahmedsignate2/kalyx-wallet/blob/main/LICENSE)). Commercial license, partnership or acquisition: **support@kalyxwallet.com** · Telegram [@kalyxntw](https://t.me/kalyxntw).

Sale documents (French): [sale dossier, IP audit, listing, white-label license template](docs/vente/README.md).

---

Copyright © 2026 KALYX. All rights reserved. Redistribution of the APK is prohibited. Decompilation and reverse engineering are prohibited **except for good-faith security research conducted under the [vulnerability disclosure program](https://github.com/ahmedsignate2/kalyx-wallet/blob/main/docs/security/VDP.md)**, which is authorized (safe harbor).
