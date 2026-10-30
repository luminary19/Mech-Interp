# Mech-Interp

Mechanistic interpretability workspace. Each child project is an independent Git
repository registered here as a submodule; the parent tracks workspace guidance
and pinned project revisions.

## Projects

| Directory | Our repository | Original upstream |
| --- | --- | --- |
| `neuron-explorer` | [luminary19/neuron-explorer](https://github.com/luminary19/neuron-explorer) | [lyramakesmusic/neuron-explorer](https://github.com/lyramakesmusic/neuron-explorer) |

## Clone the workspace

```sh
git clone --recurse-submodules https://github.com/luminary19/Mech-Interp.git
```

For an existing checkout, run `git submodule update --init --recursive`.

## Add a project

Every new project directory must be its own repository and a registered submodule.
Fork external projects into `luminary19` first, or create a standalone repository
for an original project. Then, from this workspace root:

```sh
git submodule add --force https://github.com/luminary19/PROJECT.git PROJECT
# For forks, retain the original project's URL as upstream:
git -C PROJECT remote add upstream https://github.com/ORIGINAL_OWNER/PROJECT.git
git add .gitmodules PROJECT
git commit -m "Add PROJECT submodule"
git push
```

The `--force` flag is intentional: immediate child directories are ignored by
default to prevent accidentally adding a project's source files to this parent.
Registered submodules remain tracked despite that ignore rule.

## Work on a project

Commit and push changes inside the child repository first. Then commit and push
the updated submodule pointer from this parent repository:

```sh
git -C neuron-explorer push origin main
git add neuron-explorer
git commit -m "Update neuron-explorer revision"
git push
```

Submodule checkouts from a fresh clone may have a detached HEAD. Switch to a
working branch inside the child repository before making changes.
