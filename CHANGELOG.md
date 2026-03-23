# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-03-23

### Added

- Unified CLI covering all 5 Veeam products under a single `veeam` command.
- Multi-product authentication with per-product sessions stored at `~/.config/veeam/<product>.json`.
- `veeam auth login/logout/status` for VBR, VONE, VSPC, VRO, and K10.
- Table and JSON output formats via `--format` flag.
- **VBR commands:**
  - `veeam vbr server info`
  - `veeam vbr sessions list`
  - `veeam vbr repositories list`
  - `veeam vbr proxies list`
  - `veeam vbr objects list`
  - `veeam vbr restore-points list <object-id>`
  - `veeam vbr malware-events list`
  - `veeam vbr protection-groups list`
  - `veeam vbr config-backup get/start`
  - `veeam vbr license info/workloads`
- **VONE commands:**
  - `veeam vone alarms list/resolve`
  - `veeam vone alarm-templates list`
  - `veeam vone repositories list`
  - `veeam vone best-practices get`
  - `veeam vone datastores list`
  - `veeam vone vms list`
  - `veeam vone license usage`
  - `veeam vone server info`
- **VSPC commands:**
  - `veeam vspc companies list`
  - `veeam vspc company get/usage`
  - `veeam vspc backup-servers list`
  - `veeam vspc jobs list`
  - `veeam vspc vms list`
  - `veeam vspc repositories list`
  - `veeam vspc license usage`
  - `veeam vspc alarms list`
- **VRO commands:**
  - `veeam vro plans list`
  - `veeam vro plan get <id>`
  - `veeam vro readiness-check <plan-id>`
  - `veeam vro recovery-locations list`
  - `veeam vro scopes list`
  - `veeam vro runtime status <plan-id>`
  - `veeam vro license usage`
  - `veeam vro failover --plan-id <id> --confirm`
  - `veeam vro failback --plan-id <id> --confirm`
- **K10 commands:**
  - `veeam k10 clusters list`
  - `veeam k10 applications list`
  - `veeam k10 policies list/run <name>`
  - `veeam k10 profiles list`
  - `veeam k10 restore-points list [--app <name>]`
  - `veeam k10 compliance get`
  - `veeam k10 actions status <name> --type <type>`
  - `veeam k10 backup <app>`
  - `veeam k10 restore <app> --restore-point <name>`
