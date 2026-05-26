# xs2event-claude-plugins

Claude Code plugin that installs the full xs2event development plugin stack in one command.

## Installation

Install this plugin locally:

```bash
claude plugin install . --scope user
```

Or point Claude Code at the directory while testing:

```bash
claude --plugin-dir /path/to/xs2event-claude-plugins
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
