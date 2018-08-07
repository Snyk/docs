---
title: Applying your choices
---

That’s it, we’ve tackled all the issues – hurray!

Before the wizard applies the requested changes, it suggests adding two steps to your package.json workflow to keep you vulnerability free.

```console
? Add `snyk test` to package.json file to fail test on newly disclosed vulnerabilities? Yes
? Add `snyk protect` as a package.json installation hook to apply chosen patches on install? (Y/n)
```
_Package.json steps_

First, the wizard suggests adding Snyk’s test to your regular `npm test` action. If a vulnerable package was added, the test would fail, keeping you safe. The wizard will also add `snyk` as devDependency, as you’ll need it in your test or CI environment. You can use the same logic to run this test in any favourite CI/test platform.

If you’ve chosen to patch an issue, the wizard will also suggest adding `snyk protect` to the `postinstall` step. A post installation hook runs every time you install this package’s dependencies, ensuring those dependencies are always properly patched. Note that such a hook requires adding `snyk` as a dependency (not devDependency).

```console
Applying patches...
Running `npm update`...
Saving .snyk policy file...
Updating package.json...
Remembering current dependencies for future notifications...

Your policy file has been created with the actions you've selected, add it to your source control (`git add .snyk`).
To review your policy, run `snyk policy`.

You can see a snapshot of your dependencies here:
https://snyk.io/monitor/441b89f0-6e5a-40a0-9e4e-d824e51998a2

We'll notify you when relevant new vulnerabilities are disclosed.
```
_Snyk wizard applied changes._

With all the questions answered, the wizard proceeds to apply the changes. It modifies the Package.json file with any upgrade requests or hooks, runs `npm` commands to apply the changes, and stores the Snyk policy in the _.snyk_ file (you can pretty-print it by running `snyk policy`). Make sure to add this _.snyk_ file to your source control for patch and ignore instructions to apply.

Lastly, the wizard takes a snapshot of your dependencies, so it can monitor them over time.
