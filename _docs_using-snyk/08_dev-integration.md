---
title: Integrating Snyk into your dev workflow
---

<p>To continuously avoid known vulnerabilities in your dependencies, integrate Snyk into your continuous integration (a.k.a. build) system.</p>

<h3>For Node.js</h3>

1. Install the Snyk utility using `npm install -g snyk`.
2. Run `snyk wizard` in the directory of your project following the prompts which will also generate a `.snyk` policy file.
3. Ensure the `.snyk` file you generated was added to your source control (`git add .snyk`).
4. If you selected to, Snyk will include `snyk test` as part of your `npm test` command, so if there are new vulnerabilities in the future, your CI will fail, protecting you from introducing vulnerabilities to production. Alternatively, you can add `snyk test` to any other CI test platform you use.

<h3>For Ruby, Python, Java and Go CI</h3>

1. Install the Snyk utility using `npm install -g snyk`.
2. Add `snyk test` to your CI test platform

<h3>For Scala</h3>

1. Install the Snyk utility using `npm install -g snyk`.
2. Install the [sbt-dependency-graph plugin](https://github.com/jrudolph/sbt-dependency-graph).
2. Add `snyk test` to your CI test platform

<h3>Setting up automatic monitoring</h3>
If you monitor a project with Snyk, you'll get notified if your project's dependencies are affected by newly disclosed vulnerabilities. To make sure the list of dependencies we have for your project is up to date, refresh it continuously by running `snyk monitor` in your deployment process.

Configure your environment to include the `SNYK_TOKEN` environment variable. You can find your API token on the dashboard after logging in.


<h3>API token configuration</h3>

Make sure you don't check your API token into source control, to avoid exposing it to others. Instead, use your CI environment variables to configure it.

See guidance for how to do this on:

* [Travis](https://docs.travis-ci.com/user/environment-variables/)
* [Circle](https://circleci.com/docs/environment-variables/)
* [Codeship](https://codeship.com/documentation/continuous-integration/set-environment-variables/)

You can find others through an easy [Google search]( https://www.google.co.uk/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=setting+up+env+variables+in+CI).
