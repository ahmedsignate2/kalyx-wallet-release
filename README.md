# Kalyx Wallet — Releases

**Official Android releases (signed APK) of Kalyx Wallet, a non-custodial multi-chain crypto wallet.**
Source code: **[github.com/ahmedsignate2/kalyx-wallet](https://github.com/ahmedsignate2/kalyx-wallet)** · Site: **[kalyxwallet.com](https://kalyxwallet.com)** · Web dashboard: **[app.kalyxwallet.com](https://app.kalyxwallet.com)**

![Non-custodial](https://img.shields.io/badge/keys-non--custodial-2ea44f)
![No independent audit](https://img.shields.io/badge/security%20audit-none%20yet-orange)
![Android](https://img.shields.io/badge/platform-Android%20APK-3ddc84)
[![Latest release](https://img.shields.io/github/v/release/ahmedsignate2/kalyx-wallet-release?label=latest)](https://github.com/ahmedsignate2/kalyx-wallet-release/releases/latest)

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

**Updating:** download the new APK and install it over the existing app — your wallets are kept (same signing key). There are **no over-the-air updates**: the app only runs the code of the APK you installed.

iOS and browser extension: coming later.

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
- **Anti-coercion** — a **duress code** opens a decoy wallet: your real wallets, contacts and history stay invisible. A **whitelist** keeps sends to approved addresses only (changes take effect after 24 h).
- **Swap & bridge** — LI.FI and Relay (EVM, cross-chain), Jupiter (Solana), STON.fi (TON). Kalyx fee: 0.3 % on swaps, 0 % on send/receive and Earn.
- **Earn** — Aave v3, Lido, Rocket Pool, Benqi, Jito, Marinade, Tonstakers. 0 % Kalyx fee.
- **dApps** — built-in browser, **WalletConnect v2** (EVM, Solana, Bitcoin) and **TON Connect**. Every signature is simulated and explained in plain language before you give it; spending approvals can be reviewed and **revoked in bulk**.
- **Security** — AES-256-GCM with a key derived from your PIN (scrypt), Keystore storage, biometrics, growing delay after a wrong PIN (clock changes don't shorten it), auto-lock, blur in recent apps.
- **Encrypted backup** — local file or private Google Drive folder, encrypted on-device with your password. Useless without it, even to Kalyx.
- **Desktop & Telegram** — [app.kalyxwallet.com](https://app.kalyxwallet.com) and the Telegram mini app: balances, tokens, NFTs, filterable activity, market, **send / receive / swap** — every signature is still approved on your phone. Plus a **Telegram bot** for prices, gas, token scans and price alerts.
- **Copilot** — built-in assistant with your own AI key (BYOK: DeepSeek, OpenAI, Anthropic, Gemini, Groq, OpenRouter…). It never sees your keys, phrase or PIN.
- **Watch-only wallets**, account discovery on import, contacts, price alerts, **15 languages**.

---

## 🔒 Security / Sécurité

- **Non-custodial**: keys are generated and stay on your phone. No Kalyx server, no account, no access to your funds.
- **No independent audit yet.** Built and maintained by a solo developer.
- Kalyx will **never** ask for your recovery phrase, private key, PIN or password — not in the app, not by e-mail, not on Telegram.
- Report a vulnerability privately: **[SECURITY.md](https://github.com/ahmedsignate2/kalyx-wallet/blob/main/SECURITY.md)** — Telegram [@kalyxntw](https://t.me/kalyxntw) · support@kalyxwallet.com. Never in public issues.

Terms & privacy: [kalyxwallet.com/terms](https://kalyxwallet.com/terms/) · [kalyxwallet.com/privacy](https://kalyxwallet.com/privacy/)

---

## 🧪 Report a bug / Signaler un bug

- Open an **[issue](https://github.com/ahmedsignate2/kalyx-wallet-release/issues)** (app version, phone, steps, screenshot).
- From the app: *Menu → Support* generates a diagnostic ticket **with no sensitive data**.
- E-mail: **support@kalyxwallet.com**

---

## 💼 Licensing & acquisition

Kalyx source code is proprietary and available for review at [kalyx-wallet](https://github.com/ahmedsignate2/kalyx-wallet) (see its [LICENSE](https://github.com/ahmedsignate2/kalyx-wallet/blob/main/LICENSE)). Commercial license, partnership or acquisition: **support@kalyxwallet.com** · Telegram [@kalyxntw](https://t.me/kalyxntw).

---

Copyright © 2026 KALYX. All rights reserved. Unauthorized decompilation, reverse engineering or redistribution of the APK is prohibited.
