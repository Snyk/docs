---
title: Switching between organisations
---

#### On snyk.io

* Choose the organisation you want from the drop-down menu in the top navigation.
* If you add projects on snyk.io via GitHub integration, they will be added to the currently chosen organisation.

#### In the Snyk CLI

* If you have only your default organisation, any projects you add or update by running `snyk wizard` or `snyk monitor` will be automatically associated with your default organisation.
* If you have more than one organisation, you can configure which organisation newly added projects should be associated with by running `snyk config set org=orgname`. Note: `orgname` should match the name as displayed in the URL of your org in the snyk UI:  https://app.snyk.io/org/[orgname].
* If you would like to override this global configuration for individual runs of `snyk wizard` or `snyk monitor`, run `snyk monitor --org=orgname` or `snyk wizard --org=orgname`.
