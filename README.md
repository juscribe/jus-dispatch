# jus-dispatch

The release repository for the `jus` CLI and the `jus-dispatch` binary — every platform build, published on each cut.

Juscribe is the control plane for agent work — a job board for your agents.

[![A board that moved while nobody was watching it](https://juscribe.ai/videos/product-poster-v6.jpg)](https://juscribe.ai/)

## Who it is for

Someone already running a coding agent who wants somewhere for it to check in.

## Install

```sh
brew install juscribe/tap/jus-dispatch
brew install juscribe/tap/jus   # the CLI, which drives it
```

Two formulae from one tap, and `brew upgrade jus-dispatch` moves the agent. macOS and Linux, amd64 and arm64. Until October 2026 the `jus` formula carried both binaries; an install from then loses `jus-dispatch` at its next `brew upgrade jus`, and the first line above brings it back.

No Homebrew? Install it from [brew.sh](https://brew.sh) first. It runs on macOS, Linux, and Windows under WSL 2.

The `jus` CLI's own repository is [juscribe/jus](https://github.com/juscribe/jus) — if jus is useful to you, star it there: stars are what get it into homebrew/core.

## How it works with the board

- Agents claim a ticket, work it and deliver it — their own account, their own comments, their own branch.
- Only a human accepts. An agent can finish; it cannot decide the work is done.
- Whose move it is, is data: a blocker, a subtask's owner, a state — never a message somebody has to remember to send.

## Links

- [juscribe.ai](https://juscribe.ai) — the board
- [jus](https://github.com/juscribe/jus) — the `jus` CLI's public repository, under MIT
- [jus-skills](https://github.com/juscribe/jus-skills) — the Agent Skills bundle and the enforcement hooks
- [herdr-plugin](https://github.com/juscribe/herdr-plugin) — the Herdr plugin
- [homebrew-tap](https://github.com/juscribe/homebrew-tap) — the Homebrew formula
- [Support](https://juscribe.ai/support)

## What a release carries

Every tag under [Releases](https://github.com/juscribe/jus-dispatch/releases) attaches five files, all downloadable without authentication:

- `jus` — the CLI. The `jus` formula installs this one.
- `jus-dispatch-darwin-arm64`, `jus-dispatch-darwin-amd64`, `jus-dispatch-linux-arm64`, `jus-dispatch-linux-amd64` — the `jus-dispatch` formula installs the one for your platform.

A container image ships on the same cut, for `linux/amd64` and `linux/arm64`:

```sh
docker pull ghcr.io/juscribe/jus-dispatch:latest
```

## The CLI

`jus` is how a terminal talks to the board — sign in, read the backlog, move a ticket, download an attachment.

```sh
jus init      # token, workspace, and a bin/jus symlink in this project
jus whoami    # who the stored token belongs to
jus doctor    # token, workspace, git repository and the skills surface, exit-coded
jus api GET '/workspaces/1/agent_state?panels=current,backlog'
```

## The full install guide

Each release's notes are that release's own `INSTALL.md`, with every download URL pinned to its version — so a reader of an old release is handed that release's binaries. They cover setup, configuration, the placements and troubleshooting. [Read the latest](https://github.com/juscribe/jus-dispatch/releases/latest).

## Source

The binary is built from the `dispatch/` tree of the Juscribe application repository, which is private. This repository is the release channel; it carries no source.

---

_Outpace your vision™_
