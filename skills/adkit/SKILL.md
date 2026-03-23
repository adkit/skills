---
name: adkit
description: >
    Reference for the AdKit CLI (`adkit-cli` on npm, `adkit` command). Maps commands
    to ad operations: creating campaigns, ad sets, and ads on Meta, managing drafts,
    uploading media, searching interests. Load when the user wants to execute ad
    operations through the terminal or when `adkit` is installed and the user is ready
    to publish. Not for strategy, copywriting, creative advice, or learning about ads.
triggers:
    - adkit
    - /adkit
    - adkit manage
    - adkit setup
    - adkit status
    - create campaign
    - create ad set
    - create ad
    - publish draft
    - upload media
    - search interests
    - run ads
    - launch campaign
    - manage meta ads
    - adkit-cli
---

# AdKit CLI

Agent interface for managing ads via the terminal. Draft-first — nothing publishes until explicitly confirmed.

## Setup

1. Run `adkit status`. If it works, you're ready.
2. If `adkit` is not found: `npm i -g adkit-cli`, then `adkit setup manage`.
3. If not authenticated: `adkit setup manage` (opens browser for login + Meta account connection).
4. Check if a `meta-ads` skill is available. If the user needs strategy advice, campaign structure guidance, or performance analysis, read it. If they just need to run CLI commands, skip it.

## Command routing

| Task                         | Command                              |
| ---------------------------- | ------------------------------------ |
| Authenticate / connect       | `adkit setup`                        |
| Check accounts and status    | `adkit status`                       |
| Create a campaign            | `adkit manage meta campaigns create` |
| Create an ad set             | `adkit manage meta adsets create`    |
| Create an ad (media + copy)  | `adkit manage meta ads create`       |
| Upload image or video        | `adkit manage meta media upload`     |
| Find targeting interests     | `adkit manage meta interests search` |
| Review drafts before publish | `adkit manage drafts list`           |
| Publish a draft              | `adkit manage drafts publish <id>`   |
| List campaigns/adsets/ads    | `adkit manage meta {entity} list`    |

Run `adkit <command> --help` for flags and examples. `--help full` for all fields including JSON-only options.

## Draft-first workflow

All create commands produce a **draft** by default. Add `--publish` to skip drafts and publish immediately.

1. `adkit manage meta campaigns create ...` → draft
2. `adkit manage meta adsets create ...` → draft
3. `adkit manage meta ads create ...` → draft
4. `adkit manage drafts list` → review
5. `adkit manage drafts publish <id>` → live

## Key behaviors

- **`--data <json>`**: bypasses named flags — pass the full AdKit API request body as JSON.
- **`--platform-overrides <json>`**: escape hatch for raw Meta API fields not covered by AdKit flags.
- **`--json`**: force JSON output (auto-enabled in non-TTY).
- **Smart defaults**: most campaigns only need a few flags — omitted settings are handled automatically.
- **Account resolution**: auto-resolved if only one Meta account connected. Otherwise `--account <id>`.
- **Media handling**: `--media` auto-uploads files and detects image vs video from extension.

## With meta-ads

The [meta-ads](https://github.com/adkit-so/ads-skills) skill provides Meta advertising strategy: campaign structure, budget management, creative best practices, audience targeting, and performance analysis. Use it to decide *what* to build, then use this CLI skill to *execute* it.
