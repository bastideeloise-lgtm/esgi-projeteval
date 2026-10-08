# esgi-projeteval
# Plateforme Événementielle Associative

Projet d'évaluation pratique dédié à la gestion collaborative avec **Git & GitHub** dans le cadre d'un workflow professionnel (Git Flow).

---

## Membres de l'équipe

| Rôle | Nom & Prénom | Responsabilité / Fonctionnalité | Identifiant GitHub |
| :--- | :--- | :--- | :--- |
| **Étudiant 1** | *[Andrew STIENNE]* | **Fonctionnalité A :** Identité visuelle, présentation et navigation | `@Andrew STIENNE` |
| **Étudiant 2** | *[Ravaka Irinah Carène ANDRIAMAHARO]* | **Fonctionnalité B :** Catalogue des événements | `@Ca041207` |
| **Étudiant 3** | *[Eloise BASTIDE]* | **Fonctionnalité C :** Formulaire d'inscription | `@bastideeloise-lgtm` |

---

## Présentation du Projet

Ce site web statique a pour objectif de promouvoir les activités d'une association étudiante, de répertorier les événements à venir et de permettre aux étudiants de s'inscrire en ligne.

### Fonctionnalités principales
* **Présentation & Navigation :** En-tête, identité graphique, description des missions et menu responsive.
* **Catalogue d'événements :** Fiches détaillées pour au moins trois événements (titre, date, lieu, description, bouton d'inscription).
* **Formulaire d'inscription :** Formulaire interactif en front-end (coordonnées et sélection de l'événement).

---

## Stack Technique

* **Langages :** HTML5, CSS3, JavaScript (vanilla)
* **Design :** Responsive (Mobile First / adaptatif)
* **Outils collaboratifs :** Git, GitHub Projects (Kanban & Roadmap), GitHub Issues & Pull Requests

---

## Stratégie de Branches (Git Flow)

Le dépôt suit strictement le modèle **Git Flow** :

* `main` : Version stable livrée en production (protégée contre les pushs directs).
* `develop` : Branche principale d'intégration des développements en cours (protégée).
* `feature/<nom-fonctionnalite>` : Branches dédiées à chaque tâche, créées depuis `develop` puis fusionnées via Pull Request avec revue de code obligatoire.
* `release/vX.X.X` : Branche temporaire de préparation de version avant tag et fusion finale sur `main` et `develop`.

---

## Conventions & Traçabilité

* **Nommage des commits :** Conventions de type *Conventional Commits* (ex. `feat:`, `fix:`, `docs:`, `style:`).
* **Liaison des Issues :** Chaque commit et Pull Request mentionne l'Issue correspondante (ex. `Closes #1`).
* **Revues de code :**
  * Approbation obligatoire de 2 relecteurs (en trinôme) ou 1 relecteur (en binôme) avant tout merge dans `develop`.
