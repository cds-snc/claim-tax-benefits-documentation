---
layout: page
title: Technical overview
lang: en
trans_url: Aperçu technique
childPages:
  - Sub-page one
---

File taxes to access benefits is not a stand alone application, but rather requires a high level of integration with the CRA. The product retrieves individual data from the CRA database, and then displays this data to the tax-filer. The product communicates with the CRA database via an API (application programming interface). API technology allows one system to communicate with another.

Once the tax-filer authenticates themselves, the API communicates the individual’s data to the product. The product then asks the tax-filer to confirm that this information is correct. This product files tax returns through the NETFILE API — the same one used by vendor software.

As the CRA database uses legacy technology, this involves a degree of risk. This risk is mitigated by hosting the online product on cloud technology to separate it from the database. This separation allowed us to prototype different versions, without jeopardy to the CRA data. If the product had become a live service, this meant we could have continued to change the service based on user feedback.

## For developers

Our [README](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md) documentation covers:

- [Technical overview](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#technical-overview)
  - [Use of third-party services](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#use-of-third-party-services)
  - [Automated tests](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#automated-tests)
  - [Development workflow](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#development-workflow)
  - [Continuing development](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#continuing-development)
- [Getting started](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#getting-started-npm)
  - [Build and run](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#build-and-run)
  - [Run tests](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#run-tests)
- [Using Docker](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#using-docker)
- [Deploying the app](https://github.com/cds-snc/cra-claim-tax-benefits/blob/master/README.md#deploying-the-app)

{% if site.repos %}
{% include repositories.html %}
{% endif %}
