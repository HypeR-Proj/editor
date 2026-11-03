<!--
SPDX-FileCopyrightText: 2026 roolrz
SPDX-License-Identifier: Apache-2.0
-->

# editor

Fullscreen UTF-8 text editor with bounded document storage.

Editing, search and viewport state are owned here. `lib-text-ui` supplies key decoding
and screen cells; `lib-terminal` and the Native standard library provide the session and
file operations.

See the [implementation entry](src/main.rs) and [component declaration](component.json)
for the public interfaces, build dependencies and delivered artifacts.

## Usage

In a Native session with the required capabilities:

```sh
editor --help
```

## Boundaries

Accepts UTF-8 without NUL, at most 4 MiB and 131,072 lines. Search wraps over complete
candidates. Saving prepares a synced recovery copy; fallback in-place replacement is not
a power-loss transaction or concurrent-writer lock.

## Build and test

Use this checkout inside the [repo-managed workspace](https://github.com/HypeR-Proj/HypeR).
From this repository directory:

```sh
make
make test
```

An absolute `OUT=/path/to/out` selects a shared output directory. The module
entry delegates to build/system, which prepares the installed SDK and declared
dependencies. Native binaries require HypeR; host module checks cover the tests
selected by component.json. A standalone clone does not contain the workspace’s
other source repositories or Native SDK.
