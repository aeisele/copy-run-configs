# copy-run-configs

Copy the non-shared run configurations of an IntelliJ IDEA project to another project, for example a Git worktree.

IDEA stores a non-shared run configuration in `.idea/workspace.xml`. A new worktree has no copy of that file, so the configurations are missing there.

## Usage

```
cd <source project>
copy-run-configs
```

1. Select the configurations from the list, for example `1 3 5-7`, or `a` for all.
2. Select the target project: a Git worktree, a recent IDEA project, or a path.
3. Resolve each conflict: overwrite, skip, rename, or show a diff.
4. Confirm the write. The tool keeps a backup in `workspace.xml.bak`.

Close the target project in IDEA before you copy. IDEA writes its own state over `workspace.xml` when it saves.

Run `copy-run-configs --help` for the non-interactive options.

## Requirements

Python 3.9 or later. The tool uses only the standard library.

## Install

```
ln -s "$PWD/copy-run-configs" ~/.local/bin/copy-run-configs
```
