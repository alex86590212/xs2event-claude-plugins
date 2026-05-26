# xs2event-claude-plugins

Claude Code plugin that installs the full xs2event development plugin stack in one command.

## Installation

Add the marketplace and install:

```bash
claude plugin marketplace add alex86590212/xs2event-claude-plugins
claude plugin install xs2event-claude-plugins@xs2event
```

## Usage

Once installed, run the setup command inside any Claude Code session:

```
/install-plugins
```

This installs:

| Plugin | Source |
|--------|--------|
| playwright | claude-plugins-official |
| typescript-lsp | claude-plugins-official |
| context7 | claude-plugins-official |
| frontend-design | claude-plugins-official |
| superpowers | claude-plugins-official |
| andrej-karpathy-skills | forrestchang/andrej-karpathy-skills |

Restart Claude Code after the command completes to activate the new plugins.

## Plugin structure

```
xs2event-claude-plugins/
├── .claude-plugin/
│   └── plugin.json          # Plugin manifest
└── skills/
    └── install-plugins/
        └── SKILL.md         # /install-plugins slash command
```
