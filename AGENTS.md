# AGENTS.md

Guidance for coding agents working in this repository.

## Project overview

`todo-manager` is a CLI that creates Todoist projects and tasks from the sessions of a Clubspot
camp. It is archived and kept for reference.

## Development environment

mise provides the tools in `mise.toml`. Run `mise trust`, then `mise run install`.

- `mise run ci` — the CI checks: `check`, then `test`
- `mise run check` — typecheck, Prettier check, and ESLint
- `mise run format` — fix formatting with Prettier and ESLint
- `mise run test` — run the tests with vitest (there are none yet)

Run the CLI with `pnpm exec tsx src/main.ts --help`. PR titles are conventional commits, and PRs
merge by squash. Never push to `main`.

## Authentication

- Clubspot: `CLUBSPOT_EMAIL` and `CLUBSPOT_PASSWORD`, or `-u` for the email. The password has no
  short flag, because a secret on argv leaks into `ps` and shell history.
- Todoist: `TODOIST_API_TOKEN`, or `-t`.

## Testing

Tests run with vitest, in `test/**/*.test.ts`. Mock the external SDK boundary (Parse, Todoist)
and test pure logic. Don't call a live API.

## Comments

Comments explain **why**, not what. Keep them to a line or two. Write one where a reader would
otherwise get it wrong: a non-obvious constraint, a surprising API behavior, or a decision that
looks arbitrary but isn't.

- Don't narrate the code, restate the diff, or argue for the approach you chose.
- Cite an issue (`#107`) instead of recounting its discussion.
- Test each comment: if you deleted it, would a competent reader still make the same change
  correctly? If yes, delete it.

The same applies to docs:

- **Record the outcome, not the path to it.** Say what to do today, not what failed on the way.
- **No personal identifiers.** Use a role name or `<placeholder>` instead of an email address or a
  numeric account ID.
