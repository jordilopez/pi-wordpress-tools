# pi-wordpress-tools

A collection of WordPress-focused skills, tools, and agent configurations for managing WordPress sites with Pi.

## Installation

Install the project dependencies with npm:

```bash
npm install
```

This repository uses Node.js as specified in [`.nvmrc`](.nvmrc). If you use `nvm`, run:

```bash
nvm use
```

## Available skills

The project includes WordPress workflows for:

- WordPress plugin, block, theme, and REST API development.
- WordPress Playground blueprints and local `wp-env` environments.
- WP-CLI operations, PHPStan, performance analysis, and security reviews.
- WordPress Abilities API and Interactivity API development.
- Block patterns, block themes, WPDS interfaces, and plugin directory compliance.

The skill manifest is maintained at [`.pi/pi-agent-skills/manifest.json`](.pi/pi-agent-skills/manifest.json).

## Agent setup

Herdr agent definitions are installed under [`.pi/herdr-subagents/agents/`](.pi/herdr-subagents/agents/):

- **code-reviewer** — reviews correctness, readability, architecture, security, and performance.
- **security-auditor** — audits code for security vulnerabilities and hardening opportunities.
- **test-engineer** — plans and evaluates automated test coverage.
- **web-performance-auditor** — investigates frontend performance and Core Web Vitals.

Use the agents through the Pi/Herdr integration when you need focused investigation or review.

## Usage examples

Run the project from its repository directory, then use the relevant Pi skill for your task. For example:

- Use the WordPress router to classify an unfamiliar WordPress repository.
- Use the plugin development workflow when adding hooks, settings, activation, or uninstall behavior.
- Use the REST API workflow when creating or debugging `register_rest_route` endpoints.
- Use the WP-CLI and operations workflow for content, database, cache, and cron tasks.
- Use the browser testing workflow when runtime verification requires a real browser.

Follow the applicable skill instructions and verify changes with the project’s available checks before committing.

## Project structure

```text
.pi/
├── herdr-subagents/agents/  # Focused agent definitions
└── pi-agent-skills/         # Skill package manifest
AGENTS.md                    # Project conventions
README.md                    # Project documentation
```

## Development

Selected tooling and project conventions include:

- Git
- npm
- Node.js via `.nvmrc`
- Environment configuration
- Prettier
- ESLint
- EditorConfig
- TypeScript

Keep changes focused, documented, and consistent with the existing patterns. Update this README when setup, available agents, or project usage changes.

## License

This project is licensed under the MIT License.
