# DevOps Météo

![CI/CD Pipeline](https://github.com/Bakayoko99/devops_meteo/actions/workflows/ci.yml/badge.svg)

Projet DevOps ESGI construit autour du projet Data For Good **[Valorisation Donnée Météo](https://github.com/dataforgoodfr/14_ValorisationDonneeMeteo)**, inclus ici comme sous-module (`14_ValorisationDonneeMeteo/`).

## Structure

```
├── .github/workflows/ci.yml   # Atelier 1 — pipeline CI/CD (install, tests, lint, scan, build, push)
├── docker-compose.yml         # Stack complète : app (backend/frontend/nginx/db) + monitoring
├── prometheus/                # Atelier 2 — config de scrape Prometheus
├── grafana/                   # Atelier 2 — provisioning datasource + dashboard
└── 14_ValorisationDonneeMeteo/ # Sous-module : l'application météo (backend Django + frontend Nuxt)
```

## Lancer le projet en local

```bash
git clone --recurse-submodules https://github.com/Bakayoko99/devops_meteo.git
cd devops_meteo
docker compose up -d
```

- App : http://localhost (nginx)
- Prometheus : http://localhost:9090
- Grafana : http://localhost:3000

## Ateliers

| Atelier | Statut |
|---|---|
| ① Pipeline CI/CD | ✅ install → tests → lint → scan → build → push (GHCR, branche `main`) |
| ② Monitoring (Prometheus/Grafana) | ✅ stack branchée — nécessite `django-prometheus` côté backend pour des métriques réelles |
| ③ Docker Hardened Images | ⏳ à faire |
