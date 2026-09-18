# task-tui

This is a fork of [Task](https://github.com/go-task/task) that carries a terminal user interface for running tasks, proposed upstream in [go-task/task#3015](https://github.com/go-task/task/pull/3015).

The TUI shows the task navigator and the output of each task separately, which makes parallel task dependencies much easier to follow than interleaved terminal output.

This fork exists to keep that pull request up to date and to publish builds of it while it is under review.
For everything else, including issues and contributions unrelated to the TUI, use [the upstream repository](https://github.com/go-task/task).

## Install

Download the archive for your platform from the [releases](https://github.com/janluke/task-tui/releases), extract it, and put `task-tui` somewhere on your `PATH`:

```console
curl -fsSL -o task-tui.tar.gz https://github.com/janluke/task-tui/releases/latest/download/task-tui_linux_amd64.tar.gz
tar -xzf task-tui.tar.gz -C ~/.local/bin task-tui
```

The binary is named `task-tui`, so it never replaces an official `task` installation.
Start the interface with `--tui`, which pairs well with an alias:

```bash
alias tui='task-tui --tui'
```

Everything else behaves like the Task release the build is based on.

## Releases

Release tags have the form `tui-v<tui version>-task-v<task version>`, such as `tui-v0.1.0-task-v3.53.1`.
The first part is the iteration of the TUI work, the second is the Task version it is built on.
Each release lists the exact commit and the precise base version, since the branch usually sits a few commits after a Task release.

These are unofficial builds.
Official Task releases are published on [go-task/task](https://github.com/go-task/task/releases).

## Branches

| Branch | Contents |
| --- | --- |
| `tui` | The pull request branch: upstream Task plus the TUI. It is rebased on upstream and force-pushed. |
| `main` | Upstream Task plus this README and the release workflow. Upstream is merged into it, so it is never rewritten. |

Releases are cut by running the "Release TUI build" workflow from `main` and pointing it at the `tui` branch.
Release notes come from [`.github/CHANGELOG-tui.md`](CHANGELOG-tui.md) on `main`, which is written by hand: the workflow publishes the section whose heading matches the tag, and stops if there is none.
