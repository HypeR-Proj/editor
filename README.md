<!--
SPDX-FileCopyrightText: 2026 roolrz
SPDX-License-Identifier: Apache-2.0
-->

# editor

A HypeR component. See [HypeR](https://github.com/HypeR-Proj/HypeR) for
workspace setup and the installed SDK build boundary.

Ctrl-F searches forward from the next character, then wraps to the earliest
match. A match spanning the cursor remains eligible after wrapping, and a lone
match can be found again. Searches are literal and case-sensitive; they do not
join the document's end to its beginning.

## Workspace tests

Use the [HypeR workspace](https://github.com/HypeR-Proj/HypeR) to resolve dependencies:

```sh
python3 project.py test editor
```

Paths in the documentation are relative to the repo-managed workspace root.
Edit this repository and prepare the workspace again before building.
