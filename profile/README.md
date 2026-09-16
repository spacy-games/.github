<p align="center">
  <img src="https://raw.githubusercontent.com/spacy-games/.github/main/assets/logo.svg" alt="Spacy" width="120" />
</p>

<h1 align="center">Spacy</h1>

<p align="center">
  <strong>Jeu de strategie spatiale multijoueur en temps reel</strong><br/>
  Construisez votre empire, explorez la galaxie et affrontez d'autres joueurs dans un univers procedural.
</p>

<p align="center">
  <a href="https://spacy.games">Site officiel</a> &bull;
  <a href="https://discord.gg/spacy">Discord</a>
</p>

---

## Le projet

Spacy est un jeu de strategie spatiale en ligne ou les joueurs gerent des planetes, produisent des ressources, recherchent des technologies, construisent des flottes et s'affrontent en temps reel dans un univers de **10 galaxies** pouvant contenir **jusqu'a 500 systemes** de **15 positions orbitales** chacun.

Un meme compte peut jouer sur **plusieurs serveurs de jeu independants** (beta, andromede, serveurs saisonniers ou modes speciaux).

### Fonctionnalites

- **Economie & Construction** — Production de ressources, batiments avec files de construction et systeme de prerequis
- **Recherche** — Arbre technologique avec dependances et bonus progressifs
- **Chantier naval** — Vaisseaux et defenses planetaires
- **Flottes** — Missions variees : attaque, transport, espionnage, colonisation, expedition, minage d'asteroides
- **Combat en temps reel** — Moteur tick-based avec rapports detailles et replay
- **Galaxie** — Exploration multi-niveaux avec brouillard de guerre et cartographie procedurale
- **Classements & Primes** — Rankings multi-categories et systeme de bounty
- **Diplomatie & Social** — Relations diplomatiques, alliances, messagerie temps reel

---

## Architecture

Spacy repose sur une architecture **TypeScript full-stack** organisee en monorepo avec **npm workspaces** et **Git submodules**.

| Service | Description |
|---------|-------------|
| **Spacy-Landing** | Vitrine publique SSR et selecteur de serveur |
| **Spacy-Auth** | Gateway d'authentification global (OAuth, JWKS) |
| **Spacy-Frontend** | Interface joueur (1 instance par serveur de jeu) |
| **Spacy-Backend** | Game server (1 par serveur de jeu) |
| **Spacy-TickWorker** | Worker temps reel scalable horizontalement |
| **Spacy-Backoffice** | Interface d'administration centralisee |
| **Spacy-Com** | Communications communautaires |
| **SpacyTypes** | Types TypeScript partages entre tous les services |

---

## Stack technique

<p align="center">

![TypeScript](https://img.shields.io/badge/TypeScript-5.0+-3178C6?logo=typescript&logoColor=white)
![Node](https://img.shields.io/badge/Node-22-339933?logo=nodedotjs&logoColor=white)
![Vue 3](https://img.shields.io/badge/Vue-3.5-4FC08D?logo=vuedotjs&logoColor=white)
![Nuxt 4](https://img.shields.io/badge/Nuxt-4.3-00DC82?logo=nuxtdotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-4.18-000000?logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-7-DC382D?logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white)
![Socket.IO](https://img.shields.io/badge/Socket.IO-4-010101?logo=socketdotio&logoColor=white)

</p>

---

<p align="center">
  <sub>Developpe par <a href="https://github.com/spacy-games">spacy-games</a></sub>
</p>
