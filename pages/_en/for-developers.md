---
layout: page
title: For developers
lang: en
trans_url: Aperçu technique
childPages:
  - sub-page one
  - Sub-page two
---
## Technical overview

The Claim Tax Benefits (CTB) application is a server-side [express](https://expressjs.com/) application using [Pug](https://pugjs.org/api/getting-started.html) templating on the server and schnazzy [SCSS](https://sass-lang.com/) stylesheets. The application scaffolding comes from the [the express generator](https://expressjs.com/en/starter/generator.html). It assumes the existence of a backend API (to receive user data) and a cloud database (for storing access codes), although both are stubbed out so the application can run in isolation for development purposes.

test\
\
{% if site.repos %} {% include repositories.html %} {% endif %}

Check out [the README](https://github.com/cds-snc/cra-claim-tax-benefits#getting-started-npm) for the startup instructions.\
\
A sentence from Kate