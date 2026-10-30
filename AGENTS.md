# Workspace repository structure

- This is the Mech-Interp parent repository. Each child project directory must be
  an independent Git repository registered as a submodule.
- Do not vendor child source files or add an unregistered embedded repository to
  this parent. Child directories are ignored by default to prevent this.
- For external projects, ensure a `luminary19` fork exists. Use that fork as
  `origin` and retain the original repository as `upstream` in the local checkout.
- Add new projects with `git submodule add --force <fork-url> <directory>` and
  update the project table in README.md. Commit `.gitmodules` and the gitlink.
- Commit and push child changes before publishing the parent submodule pointer.
- Preserve local changes and Git history when moving or registering repositories.
