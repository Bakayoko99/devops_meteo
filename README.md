# DevOps Météo

![CI/CD Pipeline](https://github.com/Bakayoko99/devops_meteo/actions/workflows/ci.yml/badge.svg)

Projet DevOps ESGI construit autour du projet Data For Good **[Valorisation Donnée Météo](https://github.com/dataforgoodfr/14_ValorisationDonneeMeteo)**, intégré ici dans `14_ValorisationDonneeMeteo/`.

## Structure

```
├── .github/workflows/ci.yml         # Atelier 1 — pipeline CI/CD (install, tests, lint, scan, build, push)
└── 14_ValorisationDonneeMeteo/       # L'application météo (backend Django + frontend Nuxt)
    ├── backend/Dockerfile            # Atelier 3 — image durcie (dhi.io/python)
    ├── frontend/Dockerfile           # Atelier 3 — image durcie (dhi.io/node)
    ├── prometheus/                   # Atelier 2 — config de scrape Prometheus
    ├── grafana/                      # Atelier 2 — provisioning datasource + dashboard
    └── docker-compose.yml            # Stack complète : app (backend/frontend/nginx/db) + monitoring
```

## Lancer le projet en local

```bash
git clone https://github.com/Bakayoko99/devops_meteo.git
cd devops_meteo/14_ValorisationDonneeMeteo
docker compose up -d
```

- App : http://localhost (nginx)
- Prometheus : http://localhost:9090
- Grafana : http://localhost:3000

## Ateliers

| Atelier | Statut |
|---|---|
| ① Pipeline CI/CD | ✅ install → tests → lint → scan → build → push (GHCR, branche `main`) |
| ② Monitoring (Prometheus/Grafana) | ✅ stack branchée, `/metrics` exposé côté backend via `django-prometheus` |
| ③ Docker Hardened Images | ✅ backend et frontend sur des bases `dhi.io` |
