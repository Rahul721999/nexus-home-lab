# Nexus Home Lab

Personal self-hosted infrastructure platform for experimenting with applications, container orchestration, networking, and deployment automation.

## Objectives

- Host experimental projects and personal applications.
- Manage infrastructure through Git.
- Deploy containerized applications using Kubernetes.
- Provide public access through Cloudflare Tunnel.
- Manage internal traffic through Traefik.
- Support manual and automated deployment workflows.
- Maintain persistent storage, backups, and recovery procedures.

## Infrastructure

| Component | Technology |
| --- | --- |
| Host OS | Windows 11 Pro |
| Container Runtime | Docker Desktop |
| Orchestration | Kubernetes |
| Ingress Controller | Traefik |
| Public Connectivity | Cloudflare Tunnel |
| Private Connectivity | Tailscale |
| Container Registry | Docker Hub |
| Source Control | GitHub |
| Deployment | Helm and kubectl |
| Automation | PowerShell and GitHub Actions |

## Repository Structure

- `infrastructure/` — Infrastructure configurations.
- `scripts/` — Deployment and administration scripts.
- `docs/` — Architecture and operational documentation.
- `.github/` — CI/CD workflows.

## Deployment Strategy

Infrastructure and applications are initially deployed manually using Helm and kubectl.

GitHub Actions and GitOps workflows may be introduced later.

## Security

- Never commit credentials, API tokens, or private keys.
- Keep administrative services private.
- Use persistent storage for stateful applications.
- Maintain backups outside the host machine.


## Repo Structure

```

nexus-home-lab/
│
├── README.md
├── .gitignore
│
├── infrastructure/
│   │
│   ├── kubernetes/
│   │   ├── namespaces/
│   │   │   └── apps.yaml
│   │   │
│   │   └── traefik/ ----- (Internal traffic manager)
│   │       ├── values.yaml
│   │       └── README.md
│   │
│   ├── cloudflare/ ----- (External traffic manager)
│   │   ├── deployment.yaml
│   │   └── README.md
│   │
│   └── storage/
│       └── README.md
│
├── applications/
│   └── hello-service/
│       ├── deployment.yaml
│       ├── service.yaml
│       └── ingress.yaml
│
├── scripts/
│   ├── deploy.ps1
│   ├── status.ps1
│   └── rollback.ps1
│
└── docs/
    ├── architecture.md
    ├── deployment-guide.md
    └── recovery-guide.md
```