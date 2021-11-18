# _Claim tax benefits_ documentation

[_File taxes to access benefits_](https://claim-tax-benefits.herokuapp.com/start) is a web-based demonstration of a service to make tax filing faster and easier for eligible low-income Canadians. This service was designed and developed by the [Canadian Digital Service (CDS)](https://digital.canada.ca/) in partnership with the [Canada Revenue Agency (CRA)](https://www.canada.ca/en/revenue-agency.html).

This repository contains companion documentation for the project and [can be viewed here](https://cds-snc.github.io/claim-tax-benefits-documentation/information-about-claim-tax-benefits/).

## Editing the documentation

The documentation uses [Jekyll](http://jekyllrb.com/) and the [DOCter](https://github.com/cfpb/DOCter) theme.

DOCter needs Jekyll and other dependencies to run locally. These can be installed with Bundler by running the following commands.

```
gem install bundler
bundle install
```

Run Jekyll:

```
bundle exec jekyll serve
```

Open it up in your browser: <http://localhost:4000/>

### \_config.yml

Options within the `_config.yml` file allow you to control some of the site's content and left column navigation.
