---
title: npm badge
---

To show a badge for a given npm package, copy the relevant snippet below and replace "{name}" with the name of your package.

### HTML:

```html
<img src="https://snyk.io/test/npm/{name}/badge.svg" alt="Known Vulnerabilities" data-canonical-src="https://snyk.io/test/npm/{name}" style="max-width:100%;"/>
```

### Markdown:

```md
[![Known Vulnerabilities](https://snyk.io/test/npm/{name}/badge.svg)](https://snyk.io/test/npm/{name})
```

The badge will reflect the vulnerability state of the latest version of this package.
To show the vulnerability state of a specific package, you can specify the specific version in the URL.

For example, to test version `1.2.3` of package `name`, use the URL `https://snyk.io/test/npm/name/1.2.3/badge.svg`.
