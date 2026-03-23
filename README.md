# veeam-cli

Unified CLI for Veeam Backup products — VBR, ONE, VSPC, VRO, and Kasten K10.

## Installation

```bash
# npm
npm install -g @wyre-technology/veeam-cli

# homebrew
brew tap wyre-technology/wyre
brew install veeam-cli
```

## Quick Start

```bash
# Authenticate to VBR
veeam auth vbr login --host vbr.example.com --username admin --password secret

# List backup repositories
veeam vbr repositories list

# Check license
veeam vbr license info
```

## Products

### VBR — Backup & Replication
```
veeam vbr server info
veeam vbr sessions list [--limit N] [--skip N]
veeam vbr repositories list [--limit N]
veeam vbr proxies list [--limit N]
veeam vbr objects list [--limit N]
veeam vbr restore-points list <object-id> [--limit N]
veeam vbr malware-events list [--limit N]
veeam vbr protection-groups list [--limit N]
veeam vbr config-backup get
veeam vbr config-backup start --confirm
veeam vbr license info
veeam vbr license workloads
```

### ONE — Veeam ONE Monitoring
```
veeam vone server info
veeam vone alarms list
veeam vone alarms resolve <id>
veeam vone alarm-templates list
veeam vone repositories list
veeam vone vbr-repositories list
veeam vone best-practices get
veeam vone vbr-best-practices get
veeam vone datastores list
veeam vone vms list
veeam vone license usage
```

### VSPC — Service Provider Console
```
veeam vspc companies list
veeam vspc company get <id>
veeam vspc company usage <id>
veeam vspc backup-servers list
veeam vspc jobs list
veeam vspc vms list
veeam vspc repositories list
veeam vspc license usage
veeam vspc alarms list
```

### VRO — Recovery Orchestrator
```
veeam vro plans list
veeam vro plan get <id>
veeam vro readiness-check
veeam vro recovery-locations list
veeam vro scopes list
veeam vro runtime status
veeam vro license usage
veeam vro failover --plan-id <id> --confirm
veeam vro failback --plan-id <id> --confirm
```

### K10 — Kasten K10 (Kubernetes)
```
veeam k10 clusters list
veeam k10 applications list
veeam k10 policies list
veeam k10 policies run <id>
veeam k10 profiles list
veeam k10 restore-points list
veeam k10 compliance get
veeam k10 actions status <id>
veeam k10 backup <app> [--profile <name>]
veeam k10 restore <app> [--restore-point <id>]
```

## Authentication

Each product authenticates independently:

```bash
veeam auth vbr login --host <host> --username <user> --password <pass>
veeam auth vone login --host <host> --username <user> --password <pass>
veeam auth vspc login --host <host> --username <user> --password <pass>
veeam auth vro login --host <host> --username <user> --password <pass>
veeam auth k10 login --host <host> --token <token>

veeam auth <product> status
veeam auth <product> logout
```

Sessions are stored at `~/.config/veeam/<product>.json`.

### Environment Variables

| Variable | Description |
|----------|-------------|
| `VBR_HOST` | VBR server hostname |
| `VBR_USERNAME` | VBR username |
| `VBR_PASSWORD` | VBR password |
| `VBR_REJECT_UNAUTHORIZED` | Set to `false` for self-signed certs |
| `VONE_HOST` | Veeam ONE hostname |
| `VONE_USERNAME` | Veeam ONE username |
| `VONE_PASSWORD` | Veeam ONE password |
| `VSPC_HOST` | VSPC hostname |
| `VSPC_USERNAME` | VSPC username |
| `VSPC_PASSWORD` | VSPC password |
| `VRO_HOST` | VRO hostname |
| `VRO_USERNAME` | VRO username |
| `VRO_PASSWORD` | VRO password |
| `K10_HOST` | K10 endpoint |
| `K10_TOKEN` | K10 API token |

## Output Formats

All commands support `--format json` (default) or `--format table`:

```bash
veeam vbr repositories list --format table
veeam vbr sessions list --format json
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT - see [LICENSE](LICENSE).
