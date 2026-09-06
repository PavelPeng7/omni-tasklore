# Omni-Tasklore new plugin design

## Goal

Publish the current Omni Workbench functionality as a completely new Obsidian community plugin named **Omni-Tasklore**, without altering or replacing the existing Omni Workbench repository or installation.

## Plugin identity

- Display name: `Omni-Tasklore`
- Plugin ID: `omni-tasklore`
- Package name: `omni-tasklore`
- GitHub repository: `PavelPeng7/omni-tasklore`
- Initial version: `0.1.0`
- Author: `Pavel Peng`
- License: MIT

The destination folder must match the plugin ID. Runtime view and command identifiers must use the new identity so Omni-Tasklore can coexist with Omni Workbench. Existing Omni Workbench settings are not migrated or shared.

## Repository construction

Create a new Git repository with no Omni Workbench Git history. Copy the functional source, styles, build scripts, release workflow, license, and development guidance into the new repository. Exclude the original `.git` directory and generated release artifacts.

Update all current identity references in the manifest, package metadata, runtime UI strings, command and view identifiers, documentation, comments, project instructions, and project-local UI skill. Historical Omni Workbench changelog entries will not be carried over; the new changelog begins with the `0.1.0` release.

## User experience and data

The existing task, focus timer, knowledge-note, localization, and setup flows remain functionally unchanged. The visible product name becomes Omni-Tasklore. The existing Claymorphism theme, scoped `.pvd-*` selectors, responsive rules, accessibility states, and reduced-motion behavior remain intact.

Because this is a new plugin ID, Obsidian treats it as a separate installation. It receives its own plugin data file and may be enabled alongside Omni Workbench.

## Release and verification

The build must produce `dist/main.js`, `dist/manifest.json`, and `dist/styles.css`. `manifest.json`, `package.json`, `package-lock.json`, and `versions.json` must agree on version `0.1.0`.

Run `npm run release:check`, scan the destination repository for stale product identifiers and repository URLs, then create and push the public GitHub repository. Publish tag and GitHub release `0.1.0` with the three required release assets. Community-directory submission remains a final account-facing step after the repository and release are available.

## Acceptance criteria

- Omni Workbench files and Git state remain unchanged.
- Omni-Tasklore has a new Git history and the identity defined above.
- No runtime identifiers collide with Omni Workbench.
- No stale Omni Workbench, Pavel Dashboard, Focus Workbench, or old repository references remain outside intentionally explanatory migration documentation.
- Release validation passes and release assets match version `0.1.0`.
- The public GitHub repository and `0.1.0` release are accessible.
