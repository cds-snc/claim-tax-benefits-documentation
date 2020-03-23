---
layout: page
title: "Aperçu technique"
lang: fr
trans_url: "Technical overview"
childPages:
  - Continuer le développement
---

L’application pour produire une déclaration afin d’obtenir des avantages n’est pas une application autonome et requiert un niveau d’intégration avec l’ARC assez élevé. Les données sur l’individu sont prises dans la base de données de l’ARC pour ensuite lui être fournies qu’il puisse produire ses impôts. La communication entre l’application et la base de données de l’ARC se fait par l’entremise d’un API (application programming interface). Cette technologie permet à un système de communiquer avec un autre.

Lorsque la personne qui produit ses impôts s’authentifie, l’API communique ses données à l’application. L’application demande ensuite à la personne de confirmer que ses informations soient exactes. Le retour d’impôts est ensuite soumis par l’application par l’entremise de l’API NETFILE, le même qui est utilisé par les solutions provenant de l’industrie.

Les risques sont élevés dû au fait que la base de données de l’ARC utilise des technologies désuètes. Ces risques sont atténués par le fait que la solution soit hébergée sur les technologies infonuagiques et séparée de la base de données. Cette séparation nous a permis de tester plusieurs versions de prototypes et ce, sans mettre les données de l’ARC en péril. Si l’application était devenu un service en direct, nous aurions pu continuer à changer le service basé sur la rétroaction des personnes qui l’utilisent.

{% if site.repos %}
{% include repositories.html %}
{% endif %}

## Pour les développeurs

- [Aperçu technique](https://crazee-docs.netlify.com/aperçu-technique/#aperçu-technique)
  - [L’utilisation de services de tierce partie](https://crazee-docs.netlify.com/aperçu-technique/#lutilisation-de-services-de-tierce-partie)
  - [Tests automatisés](https://crazee-docs.netlify.com/aperçu-technique/#tests-automatisés)
  - [Continuer le développement](https://crazee-docs.netlify.com/aperçu-technique/#continuer-le-développement)
- [Bâtir et exécuter l’application](https://crazee-docs.netlify.com/aperçu-technique/#bâtir-et-exécuter-lapplication)

## Aperçu technique

L’application Déclaration de revenus pour un accès aux prestations (DRAP) est une application [express](https://expressjs.com/fr/) du côté serveur qui utilise le langage [Pug](https://pugjs.org/api/getting-started.html) pour les gabarits et [SCSS](https://sass-lang.com/) pour les feuilles de styles. L'échafaudage de l’application vient du [Générateur d’applications Express](https://expressjs.com/fr/starter/generator.html). Il assume l’existence d’un API (backend) pour recevoir les données de l’utilisateur et d’une base de données infonuagique pour y stocker les codes d’accès, tous deux écrasés afin que l’application puisse fonctionner de façon isolée pour le développement.

L’application (DRAP) met en oeuvre plusieurs pratiques recommandées pour le développement d’applications modernes.

- L’application représente le parcours utilisateur au complet
- Elle prend pour exemples les meilleures [pratiques d'accessibilité pour les formulaires internet](https://adamsilver.io/articles/form-design-from-zero-to-hero-all-in-one-blog-post/)
- Elle a plusieurs fonctions de sécurité comme [security-minded HTTP headers](https://helmetjs.github.io/), [CSRF protection](https://github.com/expressjs/csurf), et [form validation](https://express-validator.github.io/docs/)
- Testé de fond en comble, incluant des tests [cypress](https://www.cypress.io/) bout-à-bout avec des [balayages d’accessibilité intégrés](https://github.com/avanslaars/cypress-axe)
- Inclus une pipeline d’intégration et déploiement continue (CI/CD) compatible avec les [GitHub Actions](https://github.com/features/actions)
- Peut exécuter en tant qu’application Node sur un \*nix OS ou comme conteneur [Docker](https://docs.docker.com/install/)
- Inclue le [scripts Terraform](https://github.com/cds-snc/cra-claim-tax-benefits/tree/master/scripts) pour déployer vers Azure ou AWS

### L’utilisation de services de tierce partie

Nous utilisons plus services de tierce partie pour améliorer les étapes du développement et de la sécurité continue.

- [GitHub](https://github.com/) est un service infonuagique qui stocke notre code source, suit les changements au code et facilite les revues de code.
- [GitHub Actions](https://github.com/features/actions) est un service d’intégration et déploiement continue (CI/CD) qui nous permet de [tester et déployer notre code](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/.github/workflows/testBuildDeploy.yml) directement de GitHub
  - Il y a beaucoup de services CI/CD, mais nous avons choisis GitHub Actions car il est très facile à installer et avec sa configuration de base yml il devient facile de s’en départir
- [Heroku](https://www.heroku.com/home) est une plateforme de service complètement gérée. Nous utilisons Heroku [Review Apps](https://devcenter.heroku.com/articles/github-integration-review-apps) pour bâtir des applications jetables à chaque demande de tirage, ce qui facilite la revue de code.
- [Snyk](https://snyk.io/) est un logiciel de service qui passe à travers nos dépendances pour voir s’il y a des problèmes. Nous recevons des alertes lorsque la version d’un progiciel a des vulnérabilités connues.
- [LGTM](https://lgtm.com/) est un logiciel de service qui effectue l’analyse de sécurité continuelle. Il fait une analyse à chaque demande de tirage pour des vulnérabilités potentielles de sécurité.
- [SonarQube](https://www.sonarqube.org/) est un logiciel de service pour l’analyse de qualité du code. Il analyse chaque demande de tirage pour identifier des anomalie, des failles de sécurité ou des bogues afin d’assurer un bonne pratiques de codage.

### Tests automatisés

Chaques demandes de tirage subit une suite de tests automatisés.

- [Jest](https://jestjs.io/) : Tests unitaires pour vérifier la logique interne des composants
- [ESLint](https://eslint.org/) : Linter JavaScript qui assure une uniformité du code JavaScript au travers de l’application
- [Cypress](https://www.cypress.io/) : Tests basé sur le comportement qui s’exécutent pour vérifier les étapes des parcours d’utilisateur
  - [cypress-axe](https://github.com/avanslaars/cypress-axe) : Nous effectuons un balayage de chaque page afin de vérifier les violations d’accessibilité dans le code
- [SonarQube](https://www.sonarqube.org/) : Il analyse chaque demande de tirage pour identifier des anomalie, des failles de sécurité ou des bogues afin d’assurer un bonne pratiques de codage.

### Continuer le développement

[Guide pour continuer le développement du produit](https://crazee-docs.netlify.com/continuer-le-d%C3%A9veloppement/) : Ce guide pour vous aider si vous désirez re-bâtir le service avec un nouvelle technologie ou développer et déployer le code.

## Bâtir et exécuter l’application

Veuillez vous référer à la page [README](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md) afin d’obtenir les instructions détaillées pour bâtir et exécuter l’application.

- [Pour débuter](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#getting-started-npm) (anglais seulement)
  - [Bâtir et exécuter](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#build-and-run) (anglais seulement)
  - [Exécuter les tests](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#run-tests) (anglais seulement)
- [Utiliser Docker](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#using-docker) (anglais seulement)
- [Deployer l’application](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/docs/DEPLOY.md#ex%C3%A9cuter-un-d%C3%A9ploiement-manuel)
