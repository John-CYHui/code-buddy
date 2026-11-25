# code-buddy

My Pi setup as one installable package: personal extensions and skills plus the PI WEB, pi-lens, Chrome DevTools, web-access, and subagents packages. Versions and exposed resources live in [`package.json`](package.json); there is no settings template or bootstrap script.

## Install

```sh
pi install git:github.com/John-CYHui/code-buddy
```

Pi installs this Git package's npm dependencies and loads the resources declared in `pi.extensions` and `pi.skills`. No separate Pi package installs or local npm install are required. Reload existing idle Pi sessions with `/reload` after installing or updating; new sessions pick up the package on startup.

The PI WEB extension provides `/pi-web`. Installing this package makes the command available in Pi; **running the PI WEB server is a separate action**. When you want its service, run `/pi-web install` and then `/pi-web doctor` inside Pi. PI WEB settings and authentication remain local to your machine, not in this Git repository.

## Customize

- `extensions/`: Pi agent tools, commands, and hooks that you develop.
- `skills/<name>/SKILL.md`: skills you develop.
- `package.json`: pinned third-party dependencies and the exact extension/skill paths Pi loads.

For a future PI WEB plugin, add its source and `piWeb.plugins` metadata here when there is a concrete feature. PI WEB's browser/server plugin enablement is distinct from installing Pi extensions.

Do not commit credentials, live session data, or runtime state. A Git package executes code from its dependencies: review changes before updating versions.
