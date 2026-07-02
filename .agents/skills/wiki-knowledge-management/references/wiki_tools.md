# Wiki Tools
Wiki_tools is comandlet to help you maintain the wiki.

## Build wiki outputs

Generate `change-log.md` from `change-log.json` and generate an `index.md` in every directory under the wiki root:

```sh
wiki_tools build
```

Choose the wiki root and generated file names:

```sh
wiki_tools build --root ./wiki --change-log-output changes.md --index-file-name llm-index.md
```

Each generated index lists markdown files in that directory and extracts YAML frontmatter `title` and `description` fields for LLM-friendly review.

Example source page:

```md
---
title: Deployment Guide
description: Steps for deploying the wiki tooling.
---

# Deployment Guide
```

## Change log tools

Append a change record to `change-log.json`:

```sh
wiki_tools changes add --title "Refresh FAQ" --time "2026-06-25T10:00:00Z" --author "Qing" --why "New process" --what-changed "Updated ownership notes"
```

`--time` is optional and defaults to the current ISO timestamp. The CLI also accepts the single-dash spelling from the requested command shape, for example `-title`.

## Config sources

Configure a different storage folder for future commands:

```sh
wiki_tools config set-storage-folder .wiki-data
```

This writes the storage-folder setting to `.wiki/config.json`. After that, commands without `--config-folder` read and write `change-log.json`, `change-log.md`, `config.json`, and `used-sources.json` in the configured folder.

Add a local source folder path to `config.json`:

```sh
wiki_tools config add-source ./docs-source
```

Override the storage folder for one command without changing the persisted setting:

```sh
wiki_tools --config-folder .wiki-tools config add-source ./docs-source
```

## Used and excluded sources

Record a used source file or folder and its SHA-256 hash in `used-sources.json`:

```sh
wiki_tools sources add ./docs-source/guide.md --source-root ./docs-source
```

When `--source-root` is supplied, the source path is stored relative to that root. This makes `staleness-check` compare paths relative to each configured source folder.

Record an excluded source with a reason:

```sh
wiki_tools sources exclude ./docs-source/draft.md --source-root ./docs-source --reason "Draft content"
```

You can also record an excluded source through `sources add`:

```sh
wiki_tools sources add ./docs-source/draft.md --source-root ./docs-source --exclude --reason "Draft content"
```

## Staleness check

Compare current source hashes against `used-sources.json` and print sources that are new or changed:

```sh
wiki_tools staleness-check
```

By default this scans every source folder in `config.json`. To scan folders directly:

```sh
wiki_tools staleness-check ./docs-source ./more-sources
```

Print machine-readable output:

```sh
wiki_tools staleness-check ./docs-source --json
```