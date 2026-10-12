<div align="center">

# Bernstein

**Déployer une application de vote en microservices sur Kubernetes.**

<img alt="Kubernetes" src="https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white"/> <img alt="Traefik" src="https://img.shields.io/badge/Traefik-24A1C1?style=for-the-badge&logo=traefikproxy&logoColor=white"/> <img alt="PostgreSQL" src="https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white"/> <img alt="Redis" src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white"/> <img alt="Docker" src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/> <img alt="GitHub Actions" src="https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white"/>

<sub>Projet à 2 · 2024</sub>

</div>

## Le projet en quelques mots

Une application de vote découpée en cinq briques (vote, résultats, worker, Redis, PostgreSQL) qu'il faut faire tourner proprement sur un cluster Kubernetes, avec un reverse proxy, du stockage persistant et du monitoring.

## Ce que ça fait

- Deployments, Services et ConfigMaps pour chaque brique
- **Ingress Traefik** avec RBAC dédié : `poll.dop.io` et `result.dop.io`
- **Volume persistant** pour PostgreSQL, secrets pour les identifiants
- Réplicas et limites de ressources CPU / mémoire
- **cAdvisor** en DaemonSet pour surveiller les conteneurs
- CI qui valide chaque manifeste

## Lancer le projet

```bash
cp postgres.secret.example.yaml postgres.secret.yaml   # mettre ses identifiants en base64
kubectl apply -f postgres.secret.yaml
kubectl apply -f .
```

## L'équipe

<a href="https://github.com/Wilson-Epitech/bernstein/graphs/contributors"><img src="https://contrib.rocks/image?repo=Wilson-Epitech/bernstein" alt="Contributeurs"/></a>

Wilson Bordichon, Keliane Katary

**Ma partition :** J'ai écrit tout le déploiement **PostgreSQL** (deployment, service, ConfigMap, volume), celui de **Redis**, et les **pipelines GitHub Actions** de validation.
