# Hetscale Deploy

A GitHub Action for [Hetscale](https://hetscale.com) node groups. It takes the deploy lock, records a release, reads the servers to deploy to, and reports them deployed, so a workflow needs no curl or jq of its own.

> **Status: in development.** There is no release yet. Do not reference this action from a workflow until `v1.0.0` is published here. Until then, the [GitHub Actions recipes](https://hetscale.com/docs/github-actions) call the API directly.

## What it will do

One `command` input selects one call of the [Hetscale API](https://hetscale.com/docs/api):

| Command | What it does |
|---|---|
| `lock`, `unlock` | Take and release a group's deploy lock |
| `release` | Record the release the pipeline built |
| `nodes` | List the serving servers' addresses, the servers to report, and the seed |
| `node` | Read one new server before its deploy |
| `deployed` | Report servers deployed with the release |
| `rollout` | Let Hetscale replace the older servers |
| `ready`, `failed` | Report a new server's deploy |

The action has no dependencies and no build step: the code a workflow runs is the code in this repository at the pinned commit.

## Security

See [SECURITY.md](SECURITY.md).

## License

[MIT](LICENSE)
