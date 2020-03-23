---
layout: page
title: Continuer le développement
lang: fr
trans_url: Continuing development
---

Ce document décrit comment poursuivre le développement à l'aide de cette base de code source, en plus de la structure de l'app et des technologies utilisées, pour faciliter le relancement de ce projet dans l'avenir.

Il y a principalement deux scénarios envisageables pour continuer les travaux sur ce _repository_.

1. Vous voulez déployer l'application et voir l'entièreté de son contenu, pour que vous puissiez la réécrire dans une autre technologie.
2. Vous voulez continuer le développement.

En faisant abstraction du contexte et des priorités, le premier scénario est le plus facile à expliquer, alors nous débuterons avec celui-ci.

(Note : si des détails manquent dans ce document, contactez [@pcraig3](https://github.com/pcraig3) ou [@charlesmorin](https://github.com/charlesmorin).)

## 1. Déployer l'application et voir toutes les pages

Tout ce que vous devez faire est de déployer l'application et trouver toutes les adresses (URL).

1. Premièrement, déployez l'application.
   - Consultez la page « [Bâtir et exécuter l'app](https://github.com/cds-snc/cra-claim-tax-benefits#build-and-run) » dans le `README`.
   - L'application sera disponible à l'adresse [http://localhost:3005/](http://localhost:3005/).
2. Une liste complète des adresses est disponible dans le fichier [`/config`<wbr>`/routes.config.js`](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/config/routes.config.js). L'ordre des adresses correspond à l'ordre d'exécution logique dans l'application.

Tout est bon! Allez vous chercher de la pizza. <span role="img" aria-label="pizza slice">🍕</span>

## 2. Reprendre là où nous nous sommes arrêtés

Hourra! Bienvenue dans l'application la plus branchée du gouvernement!! Pour poursuivre le développement, vous voulez vous assurer que l'application tourne rondement et que les tests réussissent. Ensuite, vous devez obligatoirement mettre à jour les dépendances pour demeurer le plus sécurisé possible.

1. Premièrement, déployez l'application.
   - Consultez la page « [Bâtir et exécuter l'app](https://github.com/cds-snc/cra-claim-tax-benefits#build-and-run) » dans le `README`.
   - L'application sera disponible à l'adresse [http://localhost:3005/](http://localhost:3005/).
2. Deuxièmement, exécutez les tests. Si les résultats sont bons, cela veut dire que l'application est en bon état.
   - Voir "[Exécuter les tests](https://github.com/cds-snc/cra-claim-tax-benefits#run-tests)" dans le `README`.
3. Mettez à jour toutes les dépendances de l'application puisqu'elles ne seront définitivement plus à jour.
   - Consultez le [processus de mise à jour des dépendances](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/docs/UPDATING-DEPENDENCIES.md#mettre-à-jour-les-dépendances)
   - Croisez-vous les doigts et espérez que ça fonctionne <span role="img" aria-label="doigts croisés">🤞</span>
4. Super! Lancez-vous dans le développement!!

### Structure du _repository_

| Répertoire                  | Usage                                                                                                                  |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `/.github`<wbr>`/workflows` | Pipelines d'intégration et livraison continue                                                                          |
| `/api`                      | Modèle (voir `user.json`)                                                                                              |
| `/bin`                      | Script d'exécution pour Node.js                                                                                        |
| `/config`                   | Configurations des modules / middleware npm utilisés                                                                   |
| `/cypress`                  | Tests et intégrations de bout en bout                                                                                  |
| `/db`                       | Conceptuellement, il s'agit de notre base de données cloud avec des codes d'accès                                      |
| `/docs`                     | Documentation technique                                                                                                |
| `/locales`                  | Fichiers de traductions pour les langues officielles (français et anglais)                                             |
| `/public`                   | Ressources statiques (images, scripts, feuilles de styles, icône de favori): tous les styles sont sous `/public/scss`. |
| `/routes`                   | Contrôleurs (routes et logique métier) et tests unitaires                                                              |
| `/schemas`                  | Schémas pour la validation des formulaires soumis (`HTTP POST`)                                                        |
| `/scripts`                  | Scripts Azure et HashiCorp Terraform pour _Infrastructure as Code (IaC)_                                               |
| `/utils`                    | Fonctions utilitaires et [middleware express](https://expressjs.com/en/guide/using-middleware.html)                    |
| `/views`                    | Fichiers de vue [Pug](https://pugjs.org/api/getting-started.html) qui se transposent en HMTL à l'exécution             |
| `/xml_output`               | Première tentative d'un modèle XML IMPÔTNET                                                                            |

### Choix technologiques

#### Développement

- Express.js (Node.js)
- Pug (technologie de vue)
- express-validator (validation des formulaires)
- SCSS (styles)
- Jest (tests unitaires)
- Cypress (tests de bout en bout)
- Morgan (_logger_ middleware pour les requêtes HTTP)
- Helmet (middleware pour le _Content Security Policy_)

#### Intégration et livraison continue

- Actions GitHub
- SonarCloud.io (SonarQube)
- Seekret (recherche de données sensibles dans le code source)
- Snyk (analyse continue de sécurité)
- Semmle/LGTM (analyse continue de sécurité)

#### Cloud

Microsoft Azure est le fournisseur de services Cloud

- Azure AppService (Offre PaaS pour déployer l'application)
- Azure Container Registry (Entrepôt pour images Docker)
- Azure KeyVault (Entrepôt pour données sensibles)
- Azure Application Insights (Mesures et journalisation)

#### Déploiement

- Azure AppService
- Docker

#### Autres sujets

- [Bâtir et exécuter l'application dans un conteneur Docker](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#using-docker)
- Déployer l'application manuellement dans Azure :
  - [à l'aide d'Azure Container Registry](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/docs/DEPLOY.md)
  - [à l'aide de Docker Hub](https://github.com/cds-snc/cra-claim-tax-benefits/blob/faccd2945ea6dee2a7c165041829d4da28b4f91b/DEPLOY.md)
- [Exécuter une analyse SonarQube](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#using-sonarqube)

S'il y a autre chose dont vous avez besoin qui ne fait pas partie de cette documentation, contactez [@pcraig3](https://github.com/pcraig3) ou [@charlesmorin](https://github.com/charlesmorin).
