> This repo is archived and kept for reference. The CYC CRM work in
> [cyc-seattle/isthmia](https://github.com/cyc-seattle/isthmia) replaces it.

# todo-manager

A CLI tool that creates Todoist projects from Clubspot camp sessions, using simple templates.

## Installation

Install [mise](https://mise.jdx.dev/getting-started.html), then:

```sh
mise trust
mise run install
```

## Running

```sh
pnpm exec tsx src/main.ts --help
pnpm exec tsx src/main.ts camp-emails --camp <camp id> --parent <project name>
```

## Authentication

Credentials are read from CLI arguments, which are also mapped to these environment variables. Get
your Todoist API token from <https://app.todoist.com/app/settings/integrations/developer>.

```sh
TODOIST_API_TOKEN="your token"
CLUBSPOT_EMAIL="your clubspot email"
CLUBSPOT_PASSWORD="your clubspot password"
```

## TODO

- Add ability to assign tasks to people automatically (Jack)
