---
layout: page
title: Technical overview
lang: en
trans_url: Aperçu technique
childPages:
  - Sub-page one
---

The Claim Tax Benefits (CTB) application is a server-side [express](https://expressjs.com/) application using [Pug](https://pugjs.org/api/getting-started.html) templating on the server and schnazzy [SCSS](https://sass-lang.com/) stylesheets. The application scaffolding comes from [the express generator](https://expressjs.com/en/starter/generator.html). It assumes the existence of a backend API (to receive user data) and a cloud database (for storing access codes), although both are stubbed out so the application can run in isolation for development purposes.

{% if site.repos %} {% include repositories.html %} {% endif %}

Check out [the README](https://github.com/cds-snc/cra-claim-tax-benefits#getting-started-npm) for the startup instructions.
