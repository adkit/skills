---
name: adkit
description: >
    Reference for the AdKit CLI (`adkit-cli` on npm, `adkit` command). Maps commands
    to ad operations: creating campaigns, ad sets/groups, and ads on Meta and Google Ads,
    managing drafts, uploading media, searching interests and keywords. Load when the user
    wants to execute ad operations through the terminal or when `adkit` is installed and
    the user is ready to publish. Not for strategy, copywriting, creative advice, or
    learning about ads.
triggers:
    - adkit
    - /adkit
    - adkit manage
    - adkit setup
    - adkit status
    - create campaign
    - create ad set
    - create ad group
    - create ad
    - publish draft
    - upload media
    - search interests
    - run ads
    - launch campaign
    - manage meta ads
    - manage google ads
    - adkit-cli
    - add keywords
    - negative keywords
    - keyword research
---

# AdKit CLI

Agent interface for managing ads via the terminal. Draft-first — nothing publishes until explicitly confirmed.

## Setup

1. Run `adkit status`. If it works, you're ready.
2. If `adkit` is not found: `npm i -g adkit-cli`, then `adkit setup manage`.
3. If not authenticated: `adkit setup manage` (opens browser for login + Meta account connection).
4. Check if a `meta-ads` skill is available. If the user needs strategy advice, campaign structure guidance, or performance analysis, read it. If they just need to run CLI commands, skip it.

## Command routing

### Meta

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

### Google Ads

| Task                               | Command                                              |
| ---------------------------------- | ---------------------------------------------------- |
| List / connect accounts            | `adkit manage google accounts list/available/connect <customer-id>` |
| Create a campaign                  | `adkit manage google campaigns create`               |
| Create an ad group                 | `adkit manage google ad-groups create`               |
| Create a responsive search ad      | `adkit manage google ads create`                     |
| Add / update / remove a keyword    | `adkit manage google keywords add/update/remove`     |
| Add / remove a negative keyword    | `adkit manage google keywords negatives add/remove`  |
| Performance results                | `adkit manage google results`                        |
| Search terms report                | `adkit manage google results search-terms`           |
| Keyword research (Keyword Planner) | `adkit manage google research keywords <query>`      |
| List / update / delete entity      | `adkit manage google {entity} list/update/delete`    |

Run `adkit <command> --help` for flags and examples. `--help full` for all fields including JSON-only options.

## Draft-first workflow

All create commands produce a **draft** by default. Add `--publish` to skip drafts and publish immediately.

**Meta** (Campaign → Ad Set → Ad):

1. `adkit manage meta campaigns create ...` → draft
2. `adkit manage meta adsets create ...` → draft
3. `adkit manage meta ads create ...` → draft
4. `adkit manage drafts list` → review
5. `adkit manage drafts publish <id>` → live

**Google** (Campaign → Ad Group → Ad + Keywords):

1. `adkit manage google campaigns create --name "..." --channel search --budget-daily 10 --countries US --account <id>` → draft
2. `adkit manage google ad-groups create --campaign <id> --name "..." --account <id>` → draft
3. `adkit manage google ads create --ad-group <id> --headlines "H1" --headlines "H2" --headlines "H3" --descriptions "D1" --descriptions "D2" --final-url https://example.com --account <id>` → draft
4. `adkit manage google keywords add --ad-group <id> --text "saas ads" --match-type phrase --account <id>` → draft
5. `adkit manage drafts list` → review
6. `adkit manage drafts publish <id>` → live

**Review URL**: `https://app.adkit.so/manage/drafts?draft={draftId}` — opens the draft detail modal for human review. For multiple drafts: `?drafts={id1},{id2}`.

## Rules

- **Never publish a draft without the user's explicit approval.** Always stop at `adkit manage drafts list` and wait for confirmation before running `publish`.
- **Reply in the same language as the user.**

## Key behaviors

- **`--data <json>`**: bypasses named flags — pass the full AdKit API request body as JSON.
- **`--platform-overrides <json>`**: escape hatch for raw Meta API fields not covered by AdKit flags.
- **`--json`**: force JSON output (auto-enabled in non-TTY).
- **Smart defaults**: most campaigns only need a few flags — omitted settings are handled automatically.
- **Account resolution**: auto-resolved if only one Meta account connected. Otherwise `--account <id>`.
- **Media handling**: `--media` auto-uploads files and detects image vs video from extension.

## With meta-ads

The [meta-ads](https://github.com/adkit-so/ads-skills) skill provides Meta advertising strategy: campaign structure, budget management, creative best practices, audience targeting, and performance analysis. Use it to decide *what* to build, then use this CLI skill to *execute* it.
