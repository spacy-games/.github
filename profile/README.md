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

Chaque service est analysé par [SonarQube](https://sonarqube.rahona.app) à chaque push, sur sa branche de travail.

| Service | Barrière qualité | Couverture | Fiabilité | Sécurité | Maintenabilité |
|---------|:---:|:---:|:---:|:---:|:---:|
| **Spacy-Landing** | [![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.landing&metric=alert_status&token=sqb_0450fa1699bedc0bfabb37d1d7a65f018291b62d)](https://sonarqube.rahona.app/dashboard?id=games.spacy.landing) | [![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.landing&metric=coverage&token=sqb_0450fa1699bedc0bfabb37d1d7a65f018291b62d)](https://sonarqube.rahona.app/dashboard?id=games.spacy.landing) | [![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.landing&metric=reliability_rating&token=sqb_0450fa1699bedc0bfabb37d1d7a65f018291b62d)](https://sonarqube.rahona.app/dashboard?id=games.spacy.landing) | [![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.landing&metric=security_rating&token=sqb_0450fa1699bedc0bfabb37d1d7a65f018291b62d)](https://sonarqube.rahona.app/dashboard?id=games.spacy.landing) | [![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.landing&metric=sqale_rating&token=sqb_0450fa1699bedc0bfabb37d1d7a65f018291b62d)](https://sonarqube.rahona.app/dashboard?id=games.spacy.landing) |
| **Spacy-Auth** | [![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.auth&metric=alert_status&token=sqb_c73586ed2ca4731917d131e6a979c693b58815d2)](https://sonarqube.rahona.app/dashboard?id=games.spacy.auth) | [![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.auth&metric=coverage&token=sqb_c73586ed2ca4731917d131e6a979c693b58815d2)](https://sonarqube.rahona.app/dashboard?id=games.spacy.auth) | [![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.auth&metric=reliability_rating&token=sqb_c73586ed2ca4731917d131e6a979c693b58815d2)](https://sonarqube.rahona.app/dashboard?id=games.spacy.auth) | [![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.auth&metric=security_rating&token=sqb_c73586ed2ca4731917d131e6a979c693b58815d2)](https://sonarqube.rahona.app/dashboard?id=games.spacy.auth) | [![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.auth&metric=sqale_rating&token=sqb_c73586ed2ca4731917d131e6a979c693b58815d2)](https://sonarqube.rahona.app/dashboard?id=games.spacy.auth) |
| **Spacy-Frontend** | [![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.frontend&metric=alert_status&token=sqb_71156c674f431da1a3a8e1baab86eb3f3dca9a40)](https://sonarqube.rahona.app/dashboard?id=games.spacy.frontend) | [![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.frontend&metric=coverage&token=sqb_71156c674f431da1a3a8e1baab86eb3f3dca9a40)](https://sonarqube.rahona.app/dashboard?id=games.spacy.frontend) | [![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.frontend&metric=reliability_rating&token=sqb_71156c674f431da1a3a8e1baab86eb3f3dca9a40)](https://sonarqube.rahona.app/dashboard?id=games.spacy.frontend) | [![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.frontend&metric=security_rating&token=sqb_71156c674f431da1a3a8e1baab86eb3f3dca9a40)](https://sonarqube.rahona.app/dashboard?id=games.spacy.frontend) | [![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.frontend&metric=sqale_rating&token=sqb_71156c674f431da1a3a8e1baab86eb3f3dca9a40)](https://sonarqube.rahona.app/dashboard?id=games.spacy.frontend) |
| **Spacy-Backend** | [![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backend&metric=alert_status&token=sqb_0f182d39b56a76e59b7b546f25298d8de427a120)](https://sonarqube.rahona.app/dashboard?id=games.spacy.backend) | [![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backend&metric=coverage&token=sqb_0f182d39b56a76e59b7b546f25298d8de427a120)](https://sonarqube.rahona.app/dashboard?id=games.spacy.backend) | [![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backend&metric=reliability_rating&token=sqb_0f182d39b56a76e59b7b546f25298d8de427a120)](https://sonarqube.rahona.app/dashboard?id=games.spacy.backend) | [![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backend&metric=security_rating&token=sqb_0f182d39b56a76e59b7b546f25298d8de427a120)](https://sonarqube.rahona.app/dashboard?id=games.spacy.backend) | [![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backend&metric=sqale_rating&token=sqb_0f182d39b56a76e59b7b546f25298d8de427a120)](https://sonarqube.rahona.app/dashboard?id=games.spacy.backend) |
| **Spacy-TickWorker** | [![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.tickworker&metric=alert_status&token=sqb_966019ec98d3490441dc96159b9bcfe114a33365)](https://sonarqube.rahona.app/dashboard?id=games.spacy.tickworker) | [![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.tickworker&metric=coverage&token=sqb_966019ec98d3490441dc96159b9bcfe114a33365)](https://sonarqube.rahona.app/dashboard?id=games.spacy.tickworker) | [![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.tickworker&metric=reliability_rating&token=sqb_966019ec98d3490441dc96159b9bcfe114a33365)](https://sonarqube.rahona.app/dashboard?id=games.spacy.tickworker) | [![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.tickworker&metric=security_rating&token=sqb_966019ec98d3490441dc96159b9bcfe114a33365)](https://sonarqube.rahona.app/dashboard?id=games.spacy.tickworker) | [![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.tickworker&metric=sqale_rating&token=sqb_966019ec98d3490441dc96159b9bcfe114a33365)](https://sonarqube.rahona.app/dashboard?id=games.spacy.tickworker) |
| **Spacy-Backoffice** | [![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backoffice&metric=alert_status&token=sqb_a019d2c8aeb02de74a7f601a80467bae8e480ad3)](https://sonarqube.rahona.app/dashboard?id=games.spacy.backoffice) | [![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backoffice&metric=coverage&token=sqb_a019d2c8aeb02de74a7f601a80467bae8e480ad3)](https://sonarqube.rahona.app/dashboard?id=games.spacy.backoffice) | [![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backoffice&metric=reliability_rating&token=sqb_a019d2c8aeb02de74a7f601a80467bae8e480ad3)](https://sonarqube.rahona.app/dashboard?id=games.spacy.backoffice) | [![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backoffice&metric=security_rating&token=sqb_a019d2c8aeb02de74a7f601a80467bae8e480ad3)](https://sonarqube.rahona.app/dashboard?id=games.spacy.backoffice) | [![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.backoffice&metric=sqale_rating&token=sqb_a019d2c8aeb02de74a7f601a80467bae8e480ad3)](https://sonarqube.rahona.app/dashboard?id=games.spacy.backoffice) |
| **Spacy-Com** | [![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.com&metric=alert_status&token=sqb_26b6486dd72eae9326a66ec01ebe2eacbf53805b)](https://sonarqube.rahona.app/dashboard?id=games.spacy.com) | [![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.com&metric=coverage&token=sqb_26b6486dd72eae9326a66ec01ebe2eacbf53805b)](https://sonarqube.rahona.app/dashboard?id=games.spacy.com) | [![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.com&metric=reliability_rating&token=sqb_26b6486dd72eae9326a66ec01ebe2eacbf53805b)](https://sonarqube.rahona.app/dashboard?id=games.spacy.com) | [![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.com&metric=security_rating&token=sqb_26b6486dd72eae9326a66ec01ebe2eacbf53805b)](https://sonarqube.rahona.app/dashboard?id=games.spacy.com) | [![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.com&metric=sqale_rating&token=sqb_26b6486dd72eae9326a66ec01ebe2eacbf53805b)](https://sonarqube.rahona.app/dashboard?id=games.spacy.com) |
| **Spacy-Desktop** | [![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.desktop&metric=alert_status&token=sqb_5a15acefca2e65ed1fb779d287282709721f5ed7)](https://sonarqube.rahona.app/dashboard?id=games.spacy.desktop) | [![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.desktop&metric=coverage&token=sqb_5a15acefca2e65ed1fb779d287282709721f5ed7)](https://sonarqube.rahona.app/dashboard?id=games.spacy.desktop) | [![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.desktop&metric=reliability_rating&token=sqb_5a15acefca2e65ed1fb779d287282709721f5ed7)](https://sonarqube.rahona.app/dashboard?id=games.spacy.desktop) | [![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.desktop&metric=security_rating&token=sqb_5a15acefca2e65ed1fb779d287282709721f5ed7)](https://sonarqube.rahona.app/dashboard?id=games.spacy.desktop) | [![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.desktop&metric=sqale_rating&token=sqb_5a15acefca2e65ed1fb779d287282709721f5ed7)](https://sonarqube.rahona.app/dashboard?id=games.spacy.desktop) |
| **SpacyTypes** | [![Quality Gate](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.types&metric=alert_status&token=sqb_23667262ab7e128c3c4d5412a6394ee60137a47c)](https://sonarqube.rahona.app/dashboard?id=games.spacy.types) | [![Coverage](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.types&metric=coverage&token=sqb_23667262ab7e128c3c4d5412a6394ee60137a47c)](https://sonarqube.rahona.app/dashboard?id=games.spacy.types) | [![Reliability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.types&metric=reliability_rating&token=sqb_23667262ab7e128c3c4d5412a6394ee60137a47c)](https://sonarqube.rahona.app/dashboard?id=games.spacy.types) | [![Security](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.types&metric=security_rating&token=sqb_23667262ab7e128c3c4d5412a6394ee60137a47c)](https://sonarqube.rahona.app/dashboard?id=games.spacy.types) | [![Maintainability](https://sonarqube.rahona.app/api/project_badges/measure?project=games.spacy.types&metric=sqale_rating&token=sqb_23667262ab7e128c3c4d5412a6394ee60137a47c)](https://sonarqube.rahona.app/dashboard?id=games.spacy.types) |

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
