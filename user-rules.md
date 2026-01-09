# WordPress Plugin Development Baseline

When generating or modifying code, default to official WordPress Coding Standards and WordPress Core best practices as the authority for all decisions (PHP, JS, CSS, HTML).

## Workspace awareness

This workspace may include a full WordPress installation with multiple plugins.

Treat WordPress core, themes, and non-active plugins as read-only context unless explicitly instructed otherwise.

Assume there is a single active plugin being worked on at a time.

## Active plugin resolution

The active plugin may be defined by a project-level mechanism (for example, a file such as .cursor/ACTIVE_PLUGIN.txt at the WordPress root).

Only propose or apply edits within the active plugin’s directory unless the user explicitly requests changes elsewhere.

If the active plugin is unclear, ask for clarification before making changes.

## Rule precedence

User Rules define global WordPress coding behavior and style.

Plugin-specific Project Rules (for example, rules located inside a plugin folder) may extend or refine expectations for that plugin.

When multiple rules apply, follow the most specific rule set first:
plugin folder rules → project/root rules → user rules.

## General

Prefer WordPress core APIs and established patterns over custom implementations.

Write readable, explicit code that matches WordPress Core style and prioritizes long-term compatibility.

Avoid clever abstractions that reduce clarity or portability.

### PHP

Prefix or namespace all functions, classes, hooks, script handles, and globals.

Use hooks and filters instead of modifying core behavior.

Follow WordPress plugin conventions for structure and loading.

Add ABSPATH guards to PHP files that could be accessed directly.

Use PHPDoc blocks for public functions, classes, and hooks.

### Blocks

Prefer block.json-based registration and standard WordPress helpers.

Keep block integration minimal and aligned with Core patterns.

If there is ambiguity:
Choose the approach most consistent with WordPress Core conventions, the WordPress Coding Standards, and the currently active plugin’s Project Rules.

If a request targets a plugin other than the active plugin:
pause and ask the user to update .cursor/ACTIVE_PLUGIN.txt (or explicitly confirm the new active plugin) before making any changes.
