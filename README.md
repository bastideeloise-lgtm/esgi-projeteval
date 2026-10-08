# Plateforme Événementielle Associative

Projet d'évaluation pratique dédié à la gestion collaborative avec **Git & GitHub** dans le cadre d'un workflow professionnel (Git Flow).

---

## Membres de l'équipe

| Pseudonyme GitHub | Nom Prénom | Rôle | Responsabilité |
| :--- | :--- | :--- | :--- |
| @Damiussy | STIENNE Andrew | Étudiant 1 | Fonctionnalité A : identité visuelle, présentation et navigation |
| @Ca041207 | ANDRIAMAHARO Ravaka Irinah Carène | Étudiant 2 | Fonctionnalité B : catalogue des événements |
| @bastideeloise-lgtm | BASTIDE Eloise | Étudiant 3 | Fonctionnalité C : formulaire d'inscription |

---

## Présentation du projet

Ce site web statique promeut les activités d'une association étudiante, répertorie les événements à venir et permet aux étudiants de s'inscrire en ligne.

### Fonctionnalités

- **A. Présentation & navigation** : en-tête, identité graphique, description des missions, menu responsive.
- **B. Catalogue d'événements** : au moins trois événements (titre, date, lieu, description, accès à l'inscription).
- **C. Formulaire d'inscription** : formulaire front-end (coordonnées et sélection d'un événement), sans backend ni stockage.

### Stack technique

- HTML5, CSS3, JavaScript (vanilla)
- Design responsive (mobile first)
- Git, GitHub (Issues, Pull Requests, Projects Kanban & Roadmap)

---

## Stratégie de branches (Git Flow)

| Branche | Rôle | Créée depuis | Fusionnée dans |
| :--- | :--- | :--- | :--- |
| `main` | Version stable en production (protégée) | - | - |
| `develop` | Intégration des développements en cours (protégée) | `main` | `release/*` |
| `feature/<nom>` | Une fonctionnalité ou amélioration | `develop` | `develop` (PR) |
| `bugfix/<nom>` | Correction d'une anomalie détectée en développement | `develop` | `develop` (PR) |
| `release/vX.Y` | Préparation de version, sans nouvelle fonctionnalité | `develop` | `main` (tag) et `develop` |
| `hotfix/vX.Y.Z` | Correction urgente de production | `main` | `main` (tag) et `develop` |

### Protections et règles

- `main` et `develop` sont protégées : aucun push direct, tout passe par une Pull Request.
- Chaque PR nécessite **2 approbations** des deux autres membres de l'équipe.
- Commits au format *Conventional Commits* (`feat:`, `fix:`, `docs:`, `style:`).
- Chaque commit et chaque PR référence une Issue (`Closes #n`).

> Si une limitation de GitHub empêche une protection technique, la règle est respectée manuellement et documentée ici : _à compléter si besoin_.

---

## Étapes du développement

1. **Planification** : création des Issues détaillées (critères de réalisation, responsables), du Project (vue Kanban et Roadmap avec dépendances).
2. **Initialisation** : dépôt, branches `main` et `develop`, protections, README.
3. **Développement des fonctionnalités** A, B et C dans des branches `feature/*`, intégrées par PR après revue.
4. **Évolution parallèle et conflit** : amélioration de l'identité visuelle (A) et adaptation mobile (B) en parallèle.
5. **Maintenance corrective** : correction du débordement des cartes d'événements sur mobile (`bugfix/*`).
6. **Release v1.0** : branche `release/v1.0`, vérifications, tag `v1.0`, fusion dans `main` et `develop`.
7. **Incident de production** : lien de navigation vers les événements cassé, `hotfix/v1.0.1`, tag `v1.0.1`, fusion dans `main` et `develop`.

---

## Choix de workflow

- **Git Flow** : il sépare clairement la version stable (`main`) du travail en cours (`develop`), et prévoit des branches dédiées pour les fonctionnalités, les corrections, les releases et les urgences de production.
- **Protection des branches** : un ruleset GitHub (`protection-main-develop`) protège `main` et `develop` : pas de push direct, pas de suppression, pas de force push, et Pull Request obligatoire avec **2 approbations**. Aucun contournement (bypass) n'est autorisé.
- **Revues croisées** : chaque PR est relue par les deux autres membres, ce qui oblige chacun à lire le code des autres et à participer à l'intégration.
- **Nommage** : `feature/<nom>`, `bugfix/<nom>`, `release/vX.Y`, `hotfix/vX.Y.Z`, `docs/<nom>` pour la documentation.
- **Traçabilité** : une Issue est créée avant chaque travail, référencée dans les commits et les PR (`Closes #n`), et suivie dans le GitHub Project (vues Kanban et Roadmap).

---

## Conflit Git et résolution

- **Branches concernées** : `feature/...` (identité visuelle) et `feature/...` (adaptation mobile)
- **Étudiants concernés** : Étudiant 1 et Étudiant 2
- **Fichier et zone en conflit** : _ex. `style.css`, bloc `nav` / variables de couleurs_
- **Origine** : les deux branches ont modifié volontairement les mêmes lignes à partir du même commit de `develop`; Git ne pouvait pas choisir automatiquement.
- **Choix de résolution** : _décrire ce qui a été conservé de chaque amélioration_
- **Coordination** : Étudiant 3 (@bastideeloise-lgtm) a coordonné l'intégration et la résolution.
- **Lien** : _PR n° ..._

---

## Versions publiées

| Tag | Date | Contenu | Lien |
| :--- | :--- | :--- | :--- |
| `v1.0` | _J08/10/2026_ | Première version stable : fonctionnalités A, B, C, correction mobile | _lien release_ |
| `v1.0.1` | _J08/10/2026_ | Correction du lien de navigation vers les événements | _lien release_ |

---

## Difficultés rencontrées

- **Conflit sur le README** lors d'une première fusion, résolu par le commit `fix: resolution conflit README`.
- **PR #3 fusionnée trop tôt dans `main`** : la fonctionnalité C a été intégrée dans `main` avant la mise en place des protections, alors qu'elle aurait dû passer par `develop`. L'historique n'a pas été réécrit ; le flux `feature` → `develop` → `release` → `main` est respecté depuis.
- **Référence d'Issue incorrecte** : les commits de la fonctionnalité C mentionnaient `closes #3`, qui est en réalité le numéro de la Pull Request et non d'une Issue. L'Issue correspondante a été créée ensuite (#6) et liée à la PR #3 pour rétablir la traçabilité.
- **Base de la PR** : GitHub propose `main` par défaut comme branche de destination ; il faut penser à choisir `develop` pour chaque PR de fonctionnalité.
- _Autres difficultés à compléter au fil du projet._

---

## Questions de synthèse

**1. Quel est l'intérêt de séparer développements en cours et versions stables ?** *(@Damiussy)*
Les versions stables restent toujours déployables, tandis que le code en cours peut être instable. Cela évite de livrer du code non testé et permet de développer sans risquer la production.

**2. Pourquoi imposer une revue de code avant intégration ?** *(@Damiussy)*
La revue détecte les erreurs et problèmes de qualité avant la fusion, partage la connaissance du code dans l'équipe et garantit qu'aucun changement n'est intégré sans validation par un tiers.

**3. Quelles situations provoquent un conflit Git et pourquoi sa résolution n'est-elle pas toujours automatique ?** *(@Damiussy)*
Un conflit apparaît quand deux branches modifient les mêmes lignes d'un fichier (ou qu'une branche modifie un fichier supprimé par l'autre). Git ne peut pas savoir quelle version est correcte ni comment combiner les intentions : une décision humaine est nécessaire.

**4. Quelle différence entre correction classique et correction urgente de production ?** *(@Ca041207)*
Une correction classique est planifiée, part de `develop` et suit le cycle normal jusqu'à la prochaine release. Une correction urgente (hotfix) part de `main`, ne contient que le correctif, et est livrée immédiatement avec un nouveau tag.

**5. Pourquoi répercuter une correction de production dans les développements en cours ?** *(@Ca041207)*
Sinon `develop` ne contiendrait pas le correctif et le bug réapparaîtrait à la prochaine release. La fusion du hotfix dans `develop` garde les deux branches cohérentes.

**6. Quel est le rôle d'une branche de release ?** *(@Ca041207)*
Elle fige un état de `develop` pour préparer la version : vérifications, corrections mineures, mise à jour de la documentation, sans nouvelles fonctionnalités. Elle est ensuite fusionnée dans `main` (avec tag) et `develop`.

**7. Comment GitHub Projects et les Issues facilitent-ils organisation et traçabilité ?** *(@bastideeloise-lgtm)*
Les Issues décrivent chaque tâche avec ses critères et son responsable; le Project (Kanban, Roadmap) montre l'avancement et les dépendances. Les références `#n` dans les commits et PR relient chaque modification à son besoin.

**8. Comment retrouver l'origine d'une modification dans l'historique GitHub ?** *(@bastideeloise-lgtm)*
Avec `git blame` ou la vue *Blame* de GitHub pour identifier le commit d'une ligne, puis le message du commit renvoie à la PR et à l'Issue associées, qui expliquent le contexte et la revue.
