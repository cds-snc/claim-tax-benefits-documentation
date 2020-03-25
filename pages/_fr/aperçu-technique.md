---
layout: page
title: Aperçu technique
lang: fr
trans_url: Technical overview
childPages:
  - Continuer le développement
---
L’application *Réclamation d’avantages fiscaux* n’est pas autonome et nécessite un niveau élevé d’intégration de la part de l’ARC. Ce produit extrait les données sur l’individu à partir de la base de données de l’ARC, puis les affiche au déclarant. La communication entre le produit et la base de données de l’ARC se fait par l’intermédiaire d’une interface de programmation d’application (API). Cette technologie permet à un système de communiquer avec un autre système.

Une fois que le déclarant s’est authentifié, l’API envoie les données à l’application. Celle-ci demande ensuite au déclarant de confirmer que l’information affichée est exacte. La déclaration de revenus est ensuite produite au moyen de l’API IMPÔTNET, c’est-à-dire la même que celle utilisée par les logiciels payants.

Étant donné que l’ARC utilise des technologies héritées, il existe un degré de risque. Ce risque est atténué par le fait que le produit en ligne est hébergé sur une technologie en nuage, de sorte qu’il est séparé de la base de données. Cette séparation nous a permis de réaliser plusieurs prototypes pour différentes versions, sans mettre en péril les données de l’ARC. Si le produit était devenu un service fonctionnel, nous aurions pu continuer à modifier le service en fonction des commentaires des utilisateurs.

{% if site.repos %} {% include repositories.html %}
{% endif %}

## Pour les développeurs

* [Aperçu technique](https://crazee-docs.netlify.com/aperçu-technique/#aperçu-technique)

  * [L’utilisation de services de tierce partie](https://crazee-docs.netlify.com/aperçu-technique/#lutilisation-de-services-de-tierce-partie)
  * [Tests automatisés](https://crazee-docs.netlify.com/aperçu-technique/#tests-automatisés)
  * [Continuer le développement](https://crazee-docs.netlify.com/aperçu-technique/#continuer-le-développement)
* [Bâtir et exécuter l’application](https://crazee-docs.netlify.com/aperçu-technique/#bâtir-et-exécuter-lapplication)

## Aperçu technique

L’application Réclamation d’avantages fiscaux (RAF) est une application [express](https://expressjs.com/fr/) côté serveur qui utilise les langages [Pug](https://pugjs.org/api/getting-started.html) pour les gabarits et [SCSS](https://sass-lang.com/) pour les feuilles de styles. L’échafaudage de l’application vient du [générateur d’applications Express](https://expressjs.com/fr/starter/generator.html). Il suppose l’existence d’une API backend (qui reçoit les données de l’utilisateur) et d’une base de données infonuagique (qui stocke les codes d’accès), bien que tous deux soient simulés afin que l’application puisse fonctionner de façon isolée pour le développement.

Comme il est mentionné dans l’introduction, l’application RAF met en œuvre plusieurs pratiques recommandées pour le développement de services Web modernes.

L’application RAF met en œuvre plusieurs pratiques recommandées pour le développement de services Web modernes.

* L’application représente un parcours utilisateur complet
* Elle prend en exemple les meilleures [pratiques d’accessibilité pour les formulaires Web](https://adamsilver.io/articles/form-design-from-zero-to-hero-all-in-one-blog-post/) 
* Elle a plusieurs fonctions de sécurité, comme des [en-têtes HTTP pour la sécurité](https://helmetjs.github.io/), la [protection CSRF](https://github.com/expressjs/csurf) et la [validation de formulaire](https://express-validator.github.io/docs/)
* Elle est testée de fond en comble, notamment par des tests [cypress](https://www.cypress.io/) bout-en-bout avec des [balayages d’accessibilité intégrés](https://github.com/avanslaars/cypress-axe)
* Elle comprend une pipeline d’intégration et de déploiement continus (CI/CD) compatible avec les [Actions Github](https://github.com/features/actions)
* Elle peut s’exécuter en tant qu’application Node sur un *nix OS ou comme conteneur [Docker](https://docs.docker.com/install/)
* Elle comprend les [scripts Terraform](https://github.com/cds-snc/cra-claim-tax-benefits/tree/master/scripts) pour les déploiements vers Azure ou AWS

### Utilisation de services tiers

Nous utilisons plusieurs services tiers pour améliorer le déroulement du développement et de la sécurité continue. 

* [GitHub](https://github.com/) est un service infonuagique qui stocke notre code source, suit les changements au code et facilite les revues de code.
* [Actions GitHub](https://github.com/features/actions) est un service d’intégration et de déploiement continus (CI/CD) qui nous permet de [tester et déployer notre code](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/.github/workflows/testBuildDeploy.yml)  directement à partir de GitHub
  * Il y a beaucoup de services CI/CD, mais nous avons choisi Actions GitHub car il est très facile à installer, et il serait facile de s’en départir en raison de sa configuration de base yml
* [Heroku](https://www.heroku.com/home) est une plateforme comme service (PaaS) complètement gérée. Nous utilisons [Review Apps](https://devcenter.heroku.com/articles/github-integration-review-apps) de Heroku pour construire des applications jetables à chaque demande de tirage, ce qui facilite la revue de code.
* [Snyk](https://snyk.io/) est un logiciel comme service qui passe à travers nos dépendances pour voir s’il y a des problèmes. Nous recevons des alertes lorsque la version d’un progiciel a des vulnérabilités connues.

* [LGTM](https://lgtm.com/) est un logiciel comme service qui effectue l’analyse continue de la sécurité. Il fait une analyse à chaque demande de tirage pour trouver les vulnérabilités de sécurité potentielles.
* [SonarQube](https://www.sonarqube.org/) est un logiciel comme service qui fait l’analyse de la qualité du code. Il analyse chaque demande de tirage pour trouver des anomalies, des failles de sécurité ou des bogues afin de garantir de bonnes pratiques de codage.

### Tests automatisés

Chaque demande de tirage subit une suite de tests automatisés.

* [Jest](https://jestjs.io/) : Tests unitaires servant à vérifier la logique interne des composants
* [ESLint](https://eslint.org/) : Linter JavaScript qui assure une uniformité du code JavaScript dans toute l’application
* [Cypress](https://www.cypress.io/) : Tests basés sur le comportement qui s’exécutent pour vérifier les étapes des parcours utilisateur
  * [cypress-axe](https://github.com/avanslaars/cypress-axe) : Nous effectuons un balayage de chaque page afin de vérifier les violations d’accessibilité dans le code
* [SonarQube](https://www.sonarqube.org/) : Il analyse chaque demande de tirage pour trouver des anomalies, des failles de sécurité ou des bogues afin de garantir de bonnes pratiques de codage.

### Continuer le développement

[Guide pour continuer le développement du produit](https://crazee-docs.netlify.com/continuer-le-d%C3%A9veloppement/) : Ce guide est là pour vous aider si vous voulez reconstruire le service avec une nouvelle technologie ou si vous voulez développer et déployer le code.

## Construire et exécuter l’application

Veuillez vous référer à la page [README](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md) afin d’obtenir les instructions détaillées pour construire et exécuter l’application.

* [Guide de démarrage](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#getting-started-npm) (anglais seulement)
  * [Construire et exécuter l'application](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#build-and-run) (anglais seulement)
  * [Exécuter les tests](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#run-tests) (anglais seulement)
* [Utilisation de Docker](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#using-docker) (anglais seulement)
* [Déploiement de l’application](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/docs/DEPLOY.md#ex%C3%A9cuter-un-d%C3%A9ploiement-manuel)