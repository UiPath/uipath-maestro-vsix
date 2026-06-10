# UiPath Maestro Flow Extension — Private Preview

> **Private Preview** · The UiPath Maestro Flow extension brings Flow building directly into your IDE. This extension plus the `uip` CLI let you build, debug, run, and deploy with **Claude, Codex, Copilot** (or others) without ever leaving VS Code or your favorite fork.

| | |
|---|---|
| ⏱️ **~10 minutes** | From zero to first prompt |
| 🧩 **VS Code · Cursor · Windsurf** | + any VS Code fork |
| 📦 **npm / npx** | CLI install |

> ⚠️ For Private Preview participants only. Maestro Flow is feature-flagged to your account and will not run from VS Code without matching access.

---

## What you'll get

- 🤖 **Your own agent choice** — drive Claude, Codex, or GitHub Copilot directly against UiPath projects from inside the editor. This is powered by the `uip` CLI, which gives whichever agent you pick the project context, auth, and commands it needs to act on your behalf.
- 🔀 **Stay within your IDE** — build Maestro Flow, Agents, HITL, and IXP directly from your own IDE with this extension. Build, debug, and run.
- 🧩 **Use in VS Code or any fork** — like Cursor, Windsurf, and others.
- 💻 **Build on Mac or Windows** — works across both platforms.

---

## Prerequisites

- **VS Code, Cursor, or another fork**
- **Your UiPath Automation Cloud account**
- **The `.vsix` preview file** — download it from the [latest release](https://github.com/UiPath/flow-vsix-releases/releases/latest)

---

## Getting started

### 1. Install the extension from the `.vsix`

Download the `.vsix` from the **[latest release](https://github.com/UiPath/flow-vsix-releases/releases/latest)** (all builds are listed under [Releases](https://github.com/UiPath/flow-vsix-releases/releases)) — works in any VS Code fork.

Open the command palette (`Cmd/Ctrl+Shift+P`) → **Extensions: Install from VSIX…** → select the file.

_(Alternatively, drag and drop the `.vsix` into the Extensions/Marketplace tab.)_

> ℹ️ Reload the window after installing (`Developer: Reload Window`) so the extension activates.

<!-- Image/GIF: installing the .vsix from the command palette -->
<!-- ![Install from VSIX](assets/install-vsix.gif) -->

### 2. Authenticate in the extension

Click the **UiPath extension** icon in the left sidebar and sign in with your account against your organization on Automation Cloud. Then select your tenant.

<!-- Image/GIF: signing in via the extension panel -->
<!-- ![Extension sign-in](assets/extension-auth.gif) -->

### 3. Create a solution

Open a new folder, create a solution, and design your first flow file. Follow the in-product getting-started to scaffold the solution structure.

<!-- Image/GIF: creating a solution and first flow file -->
<!-- ![Create a solution](assets/create-solution.gif) -->

---

## Combine with your favorite Coding Agent

### 1. Install the UiPath CLI and skills

The extension talks to the `uip` CLI to get project context and run commands. Install the CLI, then install the skills your coding agent uses.

```bash
# Install the UiPath CLI
npm install -g @uipath/cli

# Install skills via the CLI
uip skills install
```

> ⚠️ The extension looks for the CLI on your `PATH`. If you use a version manager (nvm, asdf), make sure the editor inherits the right shell environment.

### 2. Authenticate the CLI

Sign in so the CLI (and your agent) can access your projects.

```bash
uip login
```

> ℹ️ Tokens expire hourly. If you hit an auth error, just re-run `uip login`.

<!-- Image/GIF: CLI sign-in flow -->
<!-- ![Sign in](assets/cli-auth.gif) -->

### 3. Build your first Flow

Use VS Code's terminal window or an extension and start prompting and reasoning with Claude (or Codex, Copilot, or others) to construct your Flow directly in your IDE. Describe what you want to build in plain English — the agent discovers the available nodes and connectors, drafts a plan for you to confirm, generates the flow, and validates it via the CLI.

**Example prompts to try:**

| Prompt | What it builds |
|---|---|
| "Create a new Flow that sends a Slack message when a new row is added to a Google Sheet" | Connector-based automation with Integration Service nodes |
| "Build a Flow that processes invoices from my inbox in Outlook and writes the summary, total, VAT, and line items to Excel" | Multi-step automation with connectors |
| "Create a simple approval workflow that sends an email and waits for a response" | Basic Flow with out-of-the-box nodes |

<!-- GIF: prompting the agent to build a Flow end-to-end -->
<!-- ![Build a Flow](assets/flow-demo.gif) -->

---

## Troubleshooting & support

- **Extension didn't activate?** Reload the window and confirm it appears under Extensions (or restart VS Code).
- **"CLI not found"?** Run `uip --version` in the editor's integrated terminal. If it fails there, fix your `PATH` / restart the editor.
- **Auth errors?** Tokens expire hourly — re-run `uip login` and confirm your org/tenant.

**Bugs or feedback?** Both the extension and the CLI for Maestro Flow are early releases and still evolving — expect rough edges. Please send feedback and improvement requests through the `/uipath-feedback` command, by asking Claude to send feedback, or through the insider portal. Your feedback shapes GA.
