---
layout: page
title: Technical overview
lang: en
trans_url: Aperçu technique
childPages:
  - Continuing development
---

File taxes to access benefits is not a stand alone application, but rather requires a high level of integration with the CRA. The product retrieves individual data from the CRA database, and then displays this data to the tax-filer. The product communicates with the CRA database via an API (application programming interface). API technology allows one system to communicate with another.

Once the tax-filer authenticates themselves, the API communicates the individual’s data to the product. The product then asks the tax-filer to confirm that this information is correct. This product files tax returns through the NETFILE API — the same one used by vendor software.

As the CRA database uses legacy technology, this involves a degree of risk. This risk is mitigated by hosting the online product on cloud technology to separate it from the database. This separation allowed us to prototype different versions, without jeopardy to the CRA data. If the product had become a live service, this meant we could have continued to change the service based on user feedback.

{% if site.repos %}
{% include repositories.html %}
{% endif %}

## For developers

- [Technical overview](#technical-overview)
  - [Use of third-party services](#use-of-third-party-services)
  - [Automated tests](#automated-tests)
  - [Continuing development](#continuing-development)
- [Build and run the application](#build-and-run-the-application)

## Technical overview

The Claim Tax Benefits (CTB) application is a server-side [express](https://expressjs.com/) application using [Pug](https://pugjs.org/api/getting-started.html) templating on the server and [SCSS](https://sass-lang.com/) stylesheets. The application scaffolding comes from [the express generator](https://expressjs.com/en/starter/generator.html). It assumes the existence of a backend API (to receive user data) and a cloud database (for storing access codes), although both are stubbed out so the application can run in isolation for development purposes.

The CTB application implements many recommended practices for a modern web service.

- It represents the complete online user journey
- It exemplifies best-practice [web form accessibility](https://adamsilver.io/articles/form-design-from-zero-to-hero-all-in-one-blog-post/)
- It has various security features, such as [security-minded HTTP headers](https://helmetjs.github.io/), [CSRF protection](https://github.com/expressjs/csurf), and [form validation](https://express-validator.github.io/docs/)
- It is copiously tested, including end-to-end [cypress](https://www.cypress.io/) tests with [integrated accessibility scans](https://github.com/avanslaars/cypress-axe)
- It includes a Continuous Integration and Deployment (CI/CD) pipeline, compatible with [GitHub Actions](https://github.com/features/actions)
- It can run as a node app on a \*nix OS or as a [Docker](https://docs.docker.com/install/) container
- It includes [terraform scripts](https://github.com/cds-snc/cra-claim-tax-benefits/tree/master/scripts) for deploying either to Azure or AWS

### Use of third-party services

We use several third-party services for an improved development workflow and continuous security.

- [GitHub](https://github.com/) is a cloud-based service that stores our source code, tracks code changes and facilitates code reviews
- [GitHub Actions](https://github.com/features/actions) is a Continuous Integration and Deployment (CI/CD) service that allows us to [test and deploy our code](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/.github/workflows/testBuildDeploy.yml) right from GitHub
  - CI/CD services abound, but we used GitHub Actions because it was easy to set up, and with its yml-based configuration it would be easy to move away from
- [Heroku](https://www.heroku.com/home) is a fully-managed platform as a service. We use Heroku [Review Apps](https://devcenter.heroku.com/articles/github-integration-review-apps) to build disposable applications per pull request, facilitating code reviews.
- [Snyk](https://snyk.io/) is a software as a service product that scans through our dependencies for packages with known issues. It alerts us when a version of a package we’re using has a known exploit.
- [LGTM](https://lgtm.com/) is a software as a service product for continuous security analysis. It analyzes each pull request for potential security vulnerabilities.
- [SonarQube](https://www.sonarqube.org/) is a software as a service product for code quality analysis. It analyzes each pull request for code smells, potential security holes, or bugs to ensure better coding practice.

### Automated tests

All new pull requests have a suite of automated tests run against them.

- [Jest](https://jestjs.io/): Unit tests to verify correct internal logic for components
- [ESLint](https://eslint.org/): JavaScript linter that ensures uniform JS throughout the app
- [Cypress](https://www.cypress.io/): End-to-end behaviour-driven tests that run through desired user flows
  - [cypress-axe](https://github.com/avanslaars/cypress-axe): We run an accessibility scan per page (using [`axe`](https://www.deque.com/axe/)) to check for violations in the markup
- [SonarQube](https://www.sonarqube.org/) does a quality analysis gate looking for code smells, diminished code coverage, or bugs.

### Continuing development

[A walkthrough on how to continue development on this project](/continuing-development/): whether your aim is to rebuild the service in a new technology or to develop and release this codebase specifically.

## Build and run the application

Check out the [README](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md) for more detailed instructions on building and deploying the application.

- [Getting started](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#getting-started-npm)
  - [Build and run](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#build-and-run)
  - [Run tests](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#run-tests)
- [Using Docker](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#using-docker)
- [Deploying the app](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#deploying-the-app)
