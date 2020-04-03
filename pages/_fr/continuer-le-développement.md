---
layout: page
title: Continuer le développement
lang: fr
trans_url: Continuing development
---
Cette section décrit comment poursuivre le développement à l'aide de cette base de code source, en plus de la structure de l'app et des technologies utilisées, pour faciliter la reprise de ce projet dans l'avenir.

Il y a principalement deux scénarios envisageables pour continuer le développement.

1. Exécuter l'application et voir l'entièreté de son contenu pour pouvoir la reconstruire avec une autre technologie.
2. Continuer le développement spécifiquement sur ce *repository*.

(Remarque : S'il manque de précisions dans cette section, contactez [@pcraig3](https://github.com/pcraig3) ou [@charlesmorin](https://github.com/charlesmorin).)

## 1. Exécuter l'application et voir toutes les pages

Tout ce que vous avez à faire est d'exécuter l'application et trouver toutes les adresses URL.

1. Premièrement, exécutez l'application.

   * Consultez la page « [Construire et exécuter l'application](https://github.com/cds-snc/cra-claim-tax-benefits#build-and-run) » dans le `README`.
   * L'application sera disponible à l'adresse <http://localhost:3005/>.
2. Vous trouverez la liste complète des adresses URL dans le fichier [`/config`<wbr>`/routes.config.js`](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/config/routes.config.js). L'ordre des adresses correspond à l'ordre d'exécution logique dans l'application.

Tout est bon! Allez vous chercher de la pizza <span role="img" aria-label="pizza slice">🍕</span>

## 2. Continuer à utiliser notre *repository*

Pour poursuivre le développement après qu'un certain temps se soit écoulé, vous devez d'abord vous assurer que l'application tourne rondement et que les tests réussissent. Ensuite, vous devez  mettre à jour les dépendances, question de sécurité.

1. Premièrement, exécutez l'application.

   * Consultez la page « [Construire et exécuter l'application](https://github.com/cds-snc/cra-claim-tax-benefits#build-and-run) » dans le `README`.
   * L'application sera disponible à l'adresse <http://localhost:3005/>.
2. Deuxièmement, exécutez les tests. Si les résultats sont bons (ils devraient l'être), cela veut dire que l'application est en bon état.

   * Consultez « [Exécuter les tests](https://github.com/cds-snc/cra-claim-tax-benefits#run-tests) » dans le `README`.
3. Mettez à jour toutes les dépendances de l'application puisqu'elles ne seront plus à jour.

   * Consultez le processus de [mise à jour des dépendances](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/docs/UPDATING-DEPENDENCIES.md#mettre-à-jour-les-dépendances)
   * Croisez-vous les doigts et espérez que ça fonctionne <span role="img" aria-label="doigts croisés">🤞</span>
4. Super! Commencez le développement!

### Structure du *repository*

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
| `/scripts`                  | Scripts Azure et HashiCorp Terraform pour *Infrastructure as Code (IaC)*                                               |
| `/utils`                    | Fonctions utilitaires et [middleware express](https://expressjs.com/en/guide/using-middleware.html)                    |
| `/views`                    | Fichiers de vue [Pug](https://pugjs.org/api/getting-started.html) qui se transposent en HMTL à l'exécution             |
| `/xml_output`               | Première tentative d'un modèle XML IMPÔTNET                                                                            |

### Choix technologiques

#### Développement

* Express.js (Node.js)
* Pug (technologie de vue)
* express-validator (validation des formulaires)
* SCSS (styles)
* Jest (tests unitaires)
* Cypress (tests de bout en bout)
* Morgan (*logger* middleware pour les requêtes HTTP)
* Helmet (middleware pour le *Content Security Policy*)

#### Intégration et livraison continue

* Actions GitHub
* SonarCloud.io (SonarQube)
* Seekret (recherche de données sensibles dans le code source)
* Snyk (analyse continue de sécurité)
* Semmle/LGTM (analyse continue de sécurité)

#### Cloud

Microsoft Azure est le fournisseur de services Cloud

* Azure AppService (Offre PaaS pour déployer l'application)
* Azure Container Registry (Entrepôt pour images Docker)
* Azure KeyVault (Entrepôt pour données sensibles)
* Azure Application Insights (Mesures et journalisation)

#### Déploiement

* Azure AppService
* Docker

#### Autres sujets

* [Construire et exécuter l'application dans un conteneur Docker](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#using-docker)
* Déployer l'application manuellement dans Azure :

  * [à l'aide d'Azure Container Registry](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/docs/DEPLOY.md#ex%C3%A9cuter-un-d%C3%A9ploiement-manuel)
  * [à l'aide de Docker Hub](https://github.com/cds-snc/cra-claim-tax-benefits/blob/faccd2945ea6dee2a7c165041829d4da28b4f91b/DEPLOY.md)
* [Exécuter une analyse SonarQube](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#using-sonarqube)

S'il y a autre chose dont vous avez besoin qui ne fait pas partie de cette documentation, contactez [@pcraig3](https://github.com/pcraig3) ou [@charlesmorin](https://github.com/charlesmorin).