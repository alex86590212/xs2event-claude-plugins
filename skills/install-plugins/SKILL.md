---
name: install-plugins
description: Install the full xs2event Claude Code plugin stack. Use when the user types "/install-plugins", "install xs2event plugins", "set up Claude plugins", or "bootstrap Claude Code for xs2event".
argument-hint: [--scope user|project]
allowed-tools: [Bash]
---

# Install xs2event Plugin Stack

Install all Claude Code plugins required for xs2event development in a single run.

## Plugins installed

| Plugin | Marketplace |
|--------|-------------|
| playwright | claude-plugins-official |
| typescript-lsp | claude-plugins-official |
| context7 | claude-plugins-official |
| frontend-design | claude-plugins-official |
| superpowers | claude-plugins-official |
| andrej-karpathy-skills | karpathy-skills (forrestchang/andrej-karpathy-skills) |

## Instructions

Parse $ARGUMENTS for an optional `--scope` flag (default: `user`).

Run the following steps **sequentially**, printing a status line before each one:

### Step 1 — Add the karpathy-skills marketplace

```bash
claude plugin marketplace add forrestchang/andrej-karpathy-skills
```

If it exits non-zero because the marketplace already exists, print a skip message and continue — do not abort.

### Step 2 — Install each plugin

Run these commands one at a time. For each one: if the exit code is 0 print `✓ installed <name>`, if it is non-zero print `✗ failed <name>: <stderr>` and continue with the next plugin rather than aborting.

```bash
claude plugin install playwright@claude-plugins-official
claude plugin install typescript-lsp@claude-plugins-official
claude plugin install context7@claude-plugins-official
claude plugin install frontend-design@claude-plugins-official
claude plugin install superpowers@claude-plugins-official
claude plugin install andrej-karpathy-skills@karpathy-skills
```

### Step 3 — Print summary

After all installs finish, print:

```
────────────────────────────────────
xs2event plugin stack install complete
Restart Claude Code to activate new plugins.
────────────────────────────────────
```

List any plugins that failed so the user knows to retry them manually.
