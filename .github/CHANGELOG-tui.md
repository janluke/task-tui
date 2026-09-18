# Changelog

Changes to the TUI carried by this fork, relative to the Task version each
release is built on. Add an entry under `## Unreleased` as you work; when you
cut a release, rename that heading to the release tag. The release workflow
publishes the section whose heading matches the tag it is given, and fails if
there is none.

## Unreleased

## tui-v0.1.0-task-v3.53.1

First published build of the TUI.

### Added

- An interactive launcher with a filter input for picking tasks to run.
- Tree and list navigators, switched with `v`, with the tree as the default.
- An output pane per task, with a scrollbar and the scroll position on its frame.
- Task status, outcome, and duration in the navigator and the output header.
- A fullscreen output view with keyboard text selection (`v` and `V`) and copying, including copying with colours (`Y`).
- Saving task output to files, with suggested paths beside the project and a logs directory that ignores itself.
- Prompts for required variables, so Task's questions can be answered from the TUI.
- Display options configurable in `.taskrc.yml` and from the command line.

### Fixed

- Execution events are queued instead of blocking Task's callbacks, so a busy renderer no longer holds up task execution.
- Cursor movements unsupported by JetBrains terminals are avoided.
