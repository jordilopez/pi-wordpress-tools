# Architecture Decision Records

This file is the index and home for this project's ADRs. Record significant technical decisions here using sequential IDs (`ADR-001`, `ADR-002`, …), and preserve superseded decisions for historical context.

## ADRs

### ADR-001: Vendor WordPress Agent Skills as a Git Submodule

- **Status:** Accepted
- **Date:** 2025-11-10

#### Context

This project needs the official WordPress agent skills available to Pi Agent without copying or maintaining a divergent fork of the upstream content.

#### Decision

Track `https://github.com/WordPress/agent-skills` as a Git submodule at `vendor/wordpress-agent-skills`. Configure the project-level Pi settings to load its `skills/` directory directly.

#### Alternatives Considered

- **Copy the skills into this repository:** Rejected because updates would require manual synchronization and could drift from the official source.
- **Install as an npm dependency:** Rejected because the upstream repository is a skills collection rather than an npm package.
- **Use a global/user-level installation:** Rejected because the project should be reproducible for every contributor.

#### Consequences

- Cloning requires initializing submodules (`git clone --recurse-submodules` or `git submodule update --init`).
- Updating the skills is explicit and reviewable by advancing the submodule pointer.
- Pi discovers the upstream skills through `.pi/settings.json` without modifying their contents.
