---
title: "Testing .NET projects"
---

We scan .NET projects by examining your `obj/project.assets.json` file for .NET Core projects, and `packages.config` file for .NET projects to compare the specific versions of every [direct and deep dependency](https://snyk.io/docs/faqs/#about-known-vulnerabilities) in your project against our [NuGet vulnerability database](/vuln?type=nuget).
