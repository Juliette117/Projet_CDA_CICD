# CI/CD

# 🎬 Watch, Play & Listen (WPL)

**WPL** est une application web fullstack qui permet aux utilisateurs de gérer leurs médias favoris (films, séries, jeux vidéo, musiques), d’ajouter des likes, de créer des playlists, et de consulter leurs contenus à travers une interface moderne et responsive.

Ce projet a été développé dans le cadre du Titre Professionnel CDA, en architecture microservices, avec API Gateway, sécurisation JWT, bases PostgreSQL et Neo4j, et conteneurisation Docker.

---

## 🚀 Fonctionnalités principales

- 🔐 Authentification sécurisée (JWT)
- 🎞️ CRUD médias : films, séries, jeux vidéo, musiques
- 📂 Création de playlists (1 par média sauf séries : 1 par saison)
- ❤️ Système de likes sur les médias et playlists
- 🛠️ Dashboard administrateur Angular avec gestion complète
- 🔗 API Gateway centralisant les microservices

---

## 🧰 Technologies utilisées

- **Frontend** : Angular 17 + Bulma CSS  
- **Backend** : NestJS (monorepo microservices)  
- **Base SQL** : PostgreSQL (user-service)  
- **Base NoSQL** : Neo4j (media-service)  
- **API Gateway** : NestJS + REST  
- **Auth** : JWT + rôles (user/admin)  
- **CI/CD** : GitHub Actions  
- **Docker** : Conteneurisation complète  

---

## ⚙️ Installation locale

### 📦 Prérequis

- [Node.js 18+](https://nodejs.org/)
- [Docker](https://www.docker.com/)
- [Neo4j Desktop (ou Docker)](https://neo4j.com/)
- [PostgreSQL 14+](https://www.postgresql.org/)

### 🧪 Lancer en local (sans Docker)

```bash
git clone https://github.com/Juliette117/Projet_CDA_Back.git
git clone https://github.com/Juliette117/Projet_CDA_Front.git

# Installer les dépendances
npm install

# Lancer les services
npm run start:dev

```

🐳 Lancer l’application en local
Cloner le dépôt :

```bash
 
git clone https://github.com/ton-compte/wpl.git
cd wpl
Copier les fichiers .env.example vers .env dans chaque microservice :

```

```bash
 
cp .env.example .env

```
Lancer l’environnement avec Docker :

```bash
 
docker-compose up --build
Accéder aux interfaces :

Frontend : http://localhost:4200

API Gateway : http://localhost:3000/api

Neo4j Browser : http://localhost:7474

PostgreSQL : port 5432

```

🧪 Tester les API
Importer la collection Postman (tests/postman/wpl-collection.json)

Lancer les tests :

````bash
 
npm run test

````


### 🧪 Tester les APIs avec Postman


base_url = http://localhost:3000/api


Tester les endpoints :


| Méthode | Route                 | Description             |
| ------- | --------------------- | ----------------------- |
| POST    | `/auth/register`      | Créer un utilisateur    |
| POST    | `/auth/login`         | Afficher les infos du profil user connecté  |
| GET     | `/media/movies`       | Lister les films        |
| POST    | `/media/movies`       | Ajouter un film (admin) |
| POST    | `/playlist`           | Créer une playlist      |


### Lancer scan Snyk

```bash
snyk test --all projects
```