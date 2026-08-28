# Hannover Runner

Self-Hosted GitHub Actions Runner für **Lumina Network** — Backup, Restart, Start und Status.

Teil von Esslinger Consulting Inc. / Nexus. Verantwortlich: CEO Sven Normen Esslinger, Esquire.

## Labels

`self-hosted`, `linux`, `x64`, `lumina`, `hannover`

## Schnellstart (auf Hannover)

```bash
cd /opt/actions-runner
sudo ./svc.sh stop || true

TOKEN=$(gh api -X POST user/repos/digitaldesignerjazz/hannover-runner/actions/runners/registration-token --jq .token)

sudo ./config.sh --url https://github.com/digitaldesignerjazz/hannover-runner \
  --token "$TOKEN" \
  --name hannover \
  --labels self-hosted,linux,x64,lumina,hannover \
  --unattended

sudo ./svc.sh install
sudo ./svc.sh start
```

## Workflows

- `lumina-runner.yml` — Backup / Restart / Start / Status (workflow_dispatch)
- `backup-restart-start.yml` — kombiniertes Backup + Restart + Start

## Tracking

- Issue #1 (lumina-network) — Backup, Restart, Start
- Issue #2 (lumina-network) — Runner registrieren
- Issue #3 (lumina-network) — Dieses Repo
