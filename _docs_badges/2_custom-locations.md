---
title: Custom Manifest File Locations
---
By default, the badge will test against the first [valid manifest file](https://support.snyk.io/getting-started/languages-support) it detects in the root of your project.

If your manifest file is in another location other than the root of the repository, or if you have multiple manifest files that you would like to show a badge for, you can pass a `targetFile` query string parameter to direct the badge to test against another supported manifest file.

### HTML

```html
<a href="https://snyk.io/test/github/{username}/{repo}"><img src="https://snyk.io/test/github/{username}/{repo}/badge.svg?targetFile={path-to-target-file}" alt="Known Vulnerabilities" data-canonical-src="https://snyk.io/test/github/{username}/{repo}" style="max-width:100%;"/></a>
```

### Markdown:

```md
[![Known Vulnerabilities](https://snyk.io/test/github/{username}/{repo}/badge.svg)?targetFile={path-to-target-file}](https://snyk.io/test/github/{username}/{repo})
```
