<p align="center">
  <img src="https://raw.githubusercontent.com/spacy-games/.github/main/assets/logo.svg" alt="Spacy" width="120" />
</p>

<h1 align="center">Spacy</h1>

<p align="center">
  <strong>Jeu de stratégie spatiale multijoueur en temps réel</strong><br/>
  Construisez votre empire, explorez la galaxie et affrontez d'autres joueurs dans un univers procédural.
</p>

<p align="center">
  <a href="https://spacy.games">Site officiel</a> &bull;
  <a href="https://discord.gg/kgmdFc56mt">Discord</a>
</p>

---

## Le projet

Spacy est un jeu de stratégie spatiale en ligne où les joueurs gèrent des planètes, produisent des ressources, recherchent des technologies, construisent des flottes et s'affrontent en temps réel dans un univers de **10 galaxies** pouvant contenir **jusqu'à 500 systèmes** de **15 positions orbitales** chacun.

Un même compte joue sur **plusieurs serveurs de jeu indépendants** (bêta, andromede, serveurs saisonniers ou modes spéciaux), depuis le navigateur ou depuis Steam.

### Fonctionnalités

- **Économie et construction** — Production de ressources, bâtiments avec files de construction et prérequis
- **Recherche** — Arbre technologique avec dépendances et bonus progressifs
- **Chantier naval** — Vaisseaux, défenses planétaires et modules d'équipement
- **Flottes** — Attaque, transport, espionnage, Découverte des systèmes inconnus, colonisation, expédition, recyclage, minage d'astéroïdes, soutien de ses alliés
- **Combat en temps réel** — Moteur tick-par-tick avec rapports détaillés et replays
- **Galaxie** — Exploration multi-niveaux sous brouillard de guerre, cartographie procédurale
- **Alliances** — Banque d'alliance, sphère de Dyson, plans d'attaque coordonnés
- **Classements et primes** — Classements par catégorie et Bureau des primes
- **Social** — Messagerie et chat en temps réel, relations militaires, communauté Discord

---

## Architecture

Spacy repose sur une architecture **TypeScript full-stack**, organisée en monorepo de **sous-modules Git** et de **workspaces npm**.

| Service | Rôle |
|---------|------|
| **Spacy-Landing** | Vitrine publique en rendu serveur, compte joueur et sélecteur de serveur |
| **Spacy-Auth** | Identité globale : comptes, OAuth, JWKS, administration |
| **Spacy-Frontend** | Client de jeu (une instance par serveur de jeu) |
| **Spacy-Backend** | Serveur de jeu (un par serveur de jeu) |
| **Spacy-TickWorker** | Moteurs temps réel, mis à l'échelle horizontalement |
| **Spacy-Backoffice** | Administration centralisée |
| **Spacy-Com** | Bot Discord de la communauté |
| **Spacy-Desktop** | Client Steam |
| **SpacyTypes** | Code partagé entre tous les services |

---

## Santé du projet

Chaque service publie l'issue de sa dernière CI — staging sur `dev`, production sur `main` — et passe l'analyse [SonarQube](https://www.sonarsource.com/products/sonarqube/) à chaque push.

| Service | CI | Barrière qualité | Couverture | Fiabilité | Sécurité | Maintenabilité |
|---------|:---:|:---:|:---:|:---:|:---:|:---:|
| **Spacy-Landing** | ![production](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-landing-production.json) | ![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.landing&metric=alert_status&token=sqb_0450fa1699bedc0bfabb37d1d7a65f018291b62d) | ![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.landing&metric=coverage&token=sqb_0450fa1699bedc0bfabb37d1d7a65f018291b62d) | ![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.landing&metric=reliability_rating&token=sqb_0450fa1699bedc0bfabb37d1d7a65f018291b62d) | ![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.landing&metric=security_rating&token=sqb_0450fa1699bedc0bfabb37d1d7a65f018291b62d) | ![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.landing&metric=sqale_rating&token=sqb_0450fa1699bedc0bfabb37d1d7a65f018291b62d) |
| **Spacy-Auth** | ![production](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-auth-production.json) | ![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.auth&metric=alert_status&token=sqb_c73586ed2ca4731917d131e6a979c693b58815d2) | ![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.auth&metric=coverage&token=sqb_c73586ed2ca4731917d131e6a979c693b58815d2) | ![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.auth&metric=reliability_rating&token=sqb_c73586ed2ca4731917d131e6a979c693b58815d2) | ![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.auth&metric=security_rating&token=sqb_c73586ed2ca4731917d131e6a979c693b58815d2) | ![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.auth&metric=sqale_rating&token=sqb_c73586ed2ca4731917d131e6a979c693b58815d2) |
| **Spacy-Frontend** | ![staging](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-frontend-staging.json)<br/>![production](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-frontend-production.json) | ![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.frontend&metric=alert_status&token=sqb_71156c674f431da1a3a8e1baab86eb3f3dca9a40) | ![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.frontend&metric=coverage&token=sqb_71156c674f431da1a3a8e1baab86eb3f3dca9a40) | ![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.frontend&metric=reliability_rating&token=sqb_71156c674f431da1a3a8e1baab86eb3f3dca9a40) | ![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.frontend&metric=security_rating&token=sqb_71156c674f431da1a3a8e1baab86eb3f3dca9a40) | ![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.frontend&metric=sqale_rating&token=sqb_71156c674f431da1a3a8e1baab86eb3f3dca9a40) |
| **Spacy-Backend** | ![staging](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-backend-staging.json)<br/>![production](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-backend-production.json) | ![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backend&metric=alert_status&token=sqb_0f182d39b56a76e59b7b546f25298d8de427a120) | ![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backend&metric=coverage&token=sqb_0f182d39b56a76e59b7b546f25298d8de427a120) | ![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backend&metric=reliability_rating&token=sqb_0f182d39b56a76e59b7b546f25298d8de427a120) | ![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backend&metric=security_rating&token=sqb_0f182d39b56a76e59b7b546f25298d8de427a120) | ![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backend&metric=sqale_rating&token=sqb_0f182d39b56a76e59b7b546f25298d8de427a120) |
| **Spacy-TickWorker** | ![staging](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-tickworker-staging.json)<br/>![production](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-tickworker-production.json) | ![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.tickworker&metric=alert_status&token=sqb_966019ec98d3490441dc96159b9bcfe114a33365) | ![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.tickworker&metric=coverage&token=sqb_966019ec98d3490441dc96159b9bcfe114a33365) | ![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.tickworker&metric=reliability_rating&token=sqb_966019ec98d3490441dc96159b9bcfe114a33365) | ![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.tickworker&metric=security_rating&token=sqb_966019ec98d3490441dc96159b9bcfe114a33365) | ![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.tickworker&metric=sqale_rating&token=sqb_966019ec98d3490441dc96159b9bcfe114a33365) |
| **Spacy-Backoffice** | ![production](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-backoffice-production.json) | ![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backoffice&metric=alert_status&token=sqb_a019d2c8aeb02de74a7f601a80467bae8e480ad3) | ![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backoffice&metric=coverage&token=sqb_a019d2c8aeb02de74a7f601a80467bae8e480ad3) | ![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backoffice&metric=reliability_rating&token=sqb_a019d2c8aeb02de74a7f601a80467bae8e480ad3) | ![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backoffice&metric=security_rating&token=sqb_a019d2c8aeb02de74a7f601a80467bae8e480ad3) | ![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backoffice&metric=sqale_rating&token=sqb_a019d2c8aeb02de74a7f601a80467bae8e480ad3) |
| **Spacy-Com** | ![production](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-com-production.json) | ![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.com&metric=alert_status&token=sqb_26b6486dd72eae9326a66ec01ebe2eacbf53805b) | ![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.com&metric=coverage&token=sqb_26b6486dd72eae9326a66ec01ebe2eacbf53805b) | ![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.com&metric=reliability_rating&token=sqb_26b6486dd72eae9326a66ec01ebe2eacbf53805b) | ![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.com&metric=security_rating&token=sqb_26b6486dd72eae9326a66ec01ebe2eacbf53805b) | ![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.com&metric=sqale_rating&token=sqb_26b6486dd72eae9326a66ec01ebe2eacbf53805b) |
| **Spacy-Desktop** | ![ci](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-desktop-ci.json) | ![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.desktop&metric=alert_status&token=sqb_5a15acefca2e65ed1fb779d287282709721f5ed7) | ![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.desktop&metric=coverage&token=sqb_5a15acefca2e65ed1fb779d287282709721f5ed7) | ![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.desktop&metric=reliability_rating&token=sqb_5a15acefca2e65ed1fb779d287282709721f5ed7) | ![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.desktop&metric=security_rating&token=sqb_5a15acefca2e65ed1fb779d287282709721f5ed7) | ![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.desktop&metric=sqale_rating&token=sqb_5a15acefca2e65ed1fb779d287282709721f5ed7) |
| **SpacyTypes** | ![publication](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2Fspacy-games%2F.github%2Fmain%2Fbadges%2Fspacy-types-publication.json) | ![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.types&metric=alert_status&token=sqb_23667262ab7e128c3c4d5412a6394ee60137a47c) | ![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.types&metric=coverage&token=sqb_23667262ab7e128c3c4d5412a6394ee60137a47c) | ![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.types&metric=reliability_rating&token=sqb_23667262ab7e128c3c4d5412a6394ee60137a47c) | ![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.types&metric=security_rating&token=sqb_23667262ab7e128c3c4d5412a6394ee60137a47c) | ![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.types&metric=sqale_rating&token=sqb_23667262ab7e128c3c4d5412a6394ee60137a47c) |

---

## Stack technique

<p align="center">

![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white)
![Node](https://img.shields.io/badge/Node-22-339933?logo=nodedotjs&logoColor=white)
![Vue 3](https://img.shields.io/badge/Vue-3.5-4FC08D?logo=vuedotjs&logoColor=white)
![Nuxt 4](https://img.shields.io/badge/Nuxt-4.6-00DC82?logo=nuxtdotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-5-000000?logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-7-DC382D?logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white)
![Socket.IO](https://img.shields.io/badge/Socket.IO-4-010101?logo=socketdotio&logoColor=white)
![Electron](https://img.shields.io/badge/Electron-44-47848F?logo=electron&logoColor=white)

</p>

---

<p align="center">
  <sub>Développé par <a href="https://github.com/spacy-games">spacy-games</a></sub>
</p>
