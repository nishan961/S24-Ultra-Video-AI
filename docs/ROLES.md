# Roles & workflow

- **Nishan — Project owner & device tester**
  Owns the project and all final decisions. Tests builds on the Samsung S24 Ultra.

- **ChatGPT — Architect & implementer**
  Designs and implements the architecture and code, reviews changes, and troubleshoots.
  Primary working branch: `chatgpt-video-build`.

- **Juno — Repository & coordination**
  Sets up the repository, project structure, and branches, and coordinates
  GitHub development. Does not write the application code.

## Rules

- No passwords, API keys, access tokens, or private credentials are ever committed
  to this repository or shared in issues/PRs.
- New features land on `chatgpt-video-build` first and merge to `main` when stable.
