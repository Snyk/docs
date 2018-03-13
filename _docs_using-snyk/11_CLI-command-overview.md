---
title: CLI commands overview
---

```console
snyk [options] [command] [package]
```
The package argument is optional. If no package is given, Snyk will run the command against the current working directory allowing you test your non-public applications.

### Commands

```console
auth [api-token].....Sign into Snyk.
test ............... Test for any known vulnerabilities.
wizard ............. Configure your policy file to update, auto patch and
                     ignore vulnerabilities. Note: Node.js only.
protect ............ Protect your code from vulnerabilities and
                     optionally suppress specific vulnerabilities.
                     Note: Node.js only.
monitor ............ Record the state of dependencies and any vulnerabilities on snyk.io.
policy ............. Display the Snyk policy for a package.
ignore ............. Ignore an issue. For more help run `snyk help ignore`.
```

### Options

```console
--dev .............. Include devDependencies (defaults to production only).
--file=<string> .... Sets package file. For more help run `snyk help file`.
--org=<org-name> ... Associate a snapshot (or wizard snapshot) with a specific
                     organisation. For more help run `snyk help orgs`.
--ignore-policy .... Ignores and resets the state of your policy file.
--trust-policies ... Applies and uses ignore rules from your dependencies' Snyk policies,
                     otherwise ignore policies are only shown as a suggestion.
--show-vulnerable-paths=<boolean>
                     Display the dependency paths from the top level
                     dependencies, down to the vulnerable packages (defaults
                     to true). Applicable to `snyk test`.
--dry-run .......... Don't apply updates or patches during protect.
--severity-threshold=<low|medium|high>
                     Only report vulnerabilities of provided level or higher.
-q, --quiet ........ Silence all output.
-h, --help ......... This help information.
-v, --version ...... The CLI version.
```

### Examples

```console
  $ snyk test
  $ snyk test ionic@1.6.5
  $ snyk monitor --org=my-team
  $ snyk test --show-vulnerable-paths=false

```

<p class="layout-aside backdrop-glowing u--push-bottom-l u--push-top-l">
  Use <code>snyk test</code> in your test scripts. If a vulnerability is found, the process will exit with a non-zero exit code.
</p>
