# Hannover Runner — Public Registration

This repository hosts the **Hannover** self-hosted GitHub Actions runner for Lumina Network.

## Labels

`self-hosted`, `linux`, `x64`, `lumina`, `hannover`

## Register on this public repo

```bash
cd /opt/actions-runner
sudo ./svc.sh stop || true

TOKEN=$(gh api -X POST repos/digitaldesignerjazz/hannover-runner/actions/runners/registration-token --jq .token)

sudo ./config.sh --url https://github.com/digitaldesignerjazz/hannover-runner \
  --token "$TOKEN" \
  --name hannover \
  --labels self-hosted,linux,x64,lumina,hannover \
  --unattended

sudo ./svc.sh install
sudo ./svc.sh start
```

## Workflows

- `lumina-runner.yml` — backup / restart / start / status
- `backup-restart-start.yml` — combined backup + restart + start

## Tracking

- Issue #1 (lumina-network) — Backup, Restart, Start
- Issue #2 (lumina-network) — Runner registrieren
- Issue #3 (lumina-network) — Dieses Repo
