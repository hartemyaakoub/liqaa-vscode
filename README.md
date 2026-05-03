<div align="center">

# LIQAA for VS Code

**Manage your LIQAA Cloud account without leaving your editor.**

[![marketplace](https://img.shields.io/visual-studio-marketplace/v/liqaa.liqaa-vscode?style=flat-square&color=1d4ed8)](https://marketplace.visualstudio.com/items?itemName=liqaa.liqaa-vscode)
[![installs](https://img.shields.io/visual-studio-marketplace/i/liqaa.liqaa-vscode?style=flat-square)](https://marketplace.visualstudio.com/items?itemName=liqaa.liqaa-vscode)
[![license](https://img.shields.io/badge/license-MIT-475569?style=flat-square)](./LICENSE)

</div>

---

> Status: **Beta**. Submitted to the marketplace; install via `code --install-extension liqaa.liqaa-vscode-1.0.0.vsix` for now.

## Features

### 🗝️ API key manager
View, rotate, and revoke your `pk_live_*` / `sk_live_*` keys — synced with `liqaa.io/console`.

### 📋 OpenAPI explorer
Browse the [LIQAA OpenAPI 3.1 spec](https://github.com/hartemyaakoub/liqaa-openapi) inside VS Code. Click any endpoint → get sample requests in your current file's language (TypeScript, PHP, Python, Go, etc.).

### 🚀 Quick-action: "Add LIQAA to this project"
- Auto-detects your stack (Next.js / React / Vue / Vanilla / PHP / Python)
- Inserts the `<script>` tag or `npm install` command
- Adds a server-side token-exchange function in your existing handler

### 🎥 Live room inspector
View active rooms, their participants, and end them — straight from the activity bar.

### 🔔 Webhook tail
Stream webhook deliveries in the Output panel (`liqaa: Tail Webhooks`). Color-coded by event.

### ⌨️ Snippets
Dozens of LIQAA-specific snippets:
- `liqaa-init` — `LIQAA.init({ … })` skeleton
- `liqaa-token-exchange-node` — server-side token exchange (Node.js)
- `liqaa-token-exchange-php` — same for PHP/Laravel
- `liqaa-webhook-verify` — HMAC verification template
- `liqaa-react-button` — `<LIQAACallButton>` example

## Install

### From the marketplace (recommended)

```bash
code --install-extension liqaa.liqaa-vscode
```

### From source

```bash
git clone https://github.com/hartemyaakoub/liqaa-vscode.git
cd liqaa-vscode
npm install
npm run package    # produces .vsix
code --install-extension liqaa-vscode-1.0.0.vsix
```

## Configuration

Set in `.vscode/settings.json` (or User settings):

```json
{
  "liqaa.publicKey": "pk_live_…",
  "liqaa.secretKey": "sk_live_…",
  "liqaa.apiBase": "https://liqaa.io/api/public/v1",
  "liqaa.tailWebhooks.eventFilter": ["call.started", "call.ended"]
}
```

The extension prefers `liqaa.secretKey` from VS Code's secret store (`workbench.action.secretsManager`) over plain settings.

## Commands

| Command | Default keybinding |
| --- | --- |
| `liqaa: Sign in` | — |
| `liqaa: Add to project` | `Ctrl+Shift+L Ctrl+A` |
| `liqaa: Tail Webhooks` | `Ctrl+Shift+L Ctrl+W` |
| `liqaa: Open Console` | — |
| `liqaa: Issue SDK Token` | `Ctrl+Shift+L Ctrl+T` |

## Roadmap

- [ ] **Inline error decorators** — show LIQAA API errors in the editor when a fetch call fails at runtime
- [ ] **WebRTC peer inspector** — visualize ICE candidates / SDP / simulcast layers for the active connection
- [ ] **AI commit-message hints** for LIQAA-related changes
- [ ] **Embedded API playground** — try requests directly inside VS Code

## License

[MIT](./LICENSE)
