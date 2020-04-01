---
layout: page
title: Continuing development
lang: en
trans_url: Continuer le développement
---

This document describes how to continue development with this codebase — as well as the app structure and the technologies used — to make it easy to revive this work in the future.

We foresee two scenarios for continuing development:

1. Run the app and view all the pages in order to rebuild it using other technology
2. Continue development of this specific repository

(Note: if there’s anything not covered in here, get in touch with [@pcraig3](https://github.com/pcraig3) or [@charlesmorin](https://github.com/charlesmorin).)

## 1. Run the app and view all the pages

All you need to do here is run the app and then find all the URLs.

1. First, get it to boot up.
   - Check out "[Build and run](https://github.com/cds-snc/cra-claim-tax-benefits#build-and-run)" in the README.
   - The app will be running at [http://localhost:3005/](http://localhost:3005/).
2. A full list of URLs can be found in [`/config`<wbr>`/routes.config.js`](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/config/routes.config.js). They're pretty much in order, so you can see them all sequentially.

All good! Get yerself pizza. <span role="img" aria-label="pizza slice">🍕</span>

## 2. Continue using our repository

In order to pick up development after some arbitrary length of time, first you need to run the app, update all the npm dependencies, and then check that all the tests pass before doing anything else.

1. First, get it to boot up.
   - Check out "[Build and run](https://github.com/cds-snc/cra-claim-tax-benefits#build-and-run)" in the README.
   - The app will be running at [http://localhost:3005/](http://localhost:3005/).
2. Second, run the tests. If they all pass (they should), then you can continue.
   - Check "[Run tests](https://github.com/cds-snc/cra-claim-tax-benefits#run-tests)" in the README.
3. Update all the dependencies, as many will be out of date.
   - Follow our [Updating dependencies](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/docs/UPDATING-DEPENDENCIES.md) process
   - Fingers crossed it all works <span role="img" aria-label="crossed fingers">🤞</span>
4. Heck yeah! Get devving!!!

### Repository structure

| Folder                      | Purpose                                                                                          |
| --------------------------- | ------------------------------------------------------------------------------------------------ |
| `/.github`<wbr>`/workflows` | CI/CD pipelines<wbr>/workflows                                                                   |
| `/api`                      | Domain model (check out `user.json`)                                                             |
| `/bin`                      | Runtime script for Node.js                                                                       |
| `/config`                   | Configurations for the npm modules<wbr>/middleware used                                          |
| `/cypress`                  | End to end test fixtures and integrations                                                        |
| `/db`                       | Conceptually, this is our cloud DB with access codes                                             |
| `/docs`                     | Technical documentation                                                                          |
| `/locales`                  | Internationalization (i18n) keys to support both English and French official languages           |
| `/public`                   | Static resources (images, scripts, stylesheets, favicon): all our styling is in `/public/scss`.  |
| `/routes`                   | Controllers (routes and business logic) and unit tests                                           |
| `/schemas`                  | Schemas for form validation for our POST routes                                                  |
| `/scripts`                  | Azure and HashiCorp Terraform scripts for Infrastructure as Code (IaC)                           |
| `/utils`                    | Utility functions and [express middleware](https://expressjs.com/en/guide/using-middleware.html) |
| `/views`                    | [Pug](https://pugjs.org/api/getting-started.html) view files that translate to HMTL at runtime   |
| `/xml_output`               | Very early attempt at a NETFILE XML template                                                     |

### Technology Choices

#### Development

- Express.js (Node.js)
- Pug (view technology)
- express-validator (form validation)
- SCSS (styles)
- Jest (unit tests)
- Cypress (end to end testing)
- Morgan (HTTP request logger middleware)
- Helmet (Content Security Policy middleware)

#### Continuous Integration & Delivery

- GitHub Actions
- SonarCloud.io (SonarQube)
- Seekret (find secrets in code)
- Snyk (continuous security analysis)
- Semmle/LGTM (continuous security analysis)

#### Cloud

Microsoft Azure is the Cloud Service Provider (CSP)

- Azure AppService (PaaS offering to deploy the app)
- Azure Container Registry
- Azure KeyVault (Secrets)
- Azure Application Insights (Metrics and logging)

#### Deployment

- Azure AppService
- Docker

#### Other topics

- [Build and run the application as a Docker container](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#using-docker)
- Deploy the application manually on Azure:
  - [using Azure Container Registry](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/docs/DEPLOY.md)
  - [using Docker Hub](https://github.com/cds-snc/cra-claim-tax-benefits/blob/faccd2945ea6dee2a7c165041829d4da28b4f91b/DEPLOY.md)
- [Run a SonarQube analysis](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#using-sonarqube)

If there's anything else you need that's not in here, get in touch with [@pcraig3](https://github.com/pcraig3) or [@charlesmorin](https://github.com/charlesmorin).
