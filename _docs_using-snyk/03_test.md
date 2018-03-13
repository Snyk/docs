---
title: Test
---
### Test a local project
To only test your project for known vulnerabilities, browse to your project’s folder and run `snyk test`:

```console
cd ~/projects/myproj/
```

`snyk test` takes stock of all the local dependencies and queries the snyk service for related known vulnerabilities. It displays the found issues along with additional information. For Node.js projects, it also suggests remediation steps.

When `snyk test` runs, it tries to detect the appropriate file for your project by looking for the following files, in this order:

  1. yarn.lock
  1. package.json
  1. Gemfile
  1. Gemfile.lock
  1. pom.xml
  1. requirements.txt
  1. build.gradle
  1. build.sbt
  1. Gopkg.lock
  1. vendor/vendor.json
  1. obj/project.assets.json
  1. packages.config


When testing locally, you can specify the file that Snyk should inspect for package information.

```console
$ snyk test --file=package.json</span>
```

The CLI does not currently auto-detect `.sln` files, so for .NET and .NET Core projects you can specify in the `--file` parameter the location of the solution file and the CLI will run on all the projects it finds inside.

```console
$ snyk test --file=myApp.sln</span>
```

### Setting severity threshold
To have a better control over your tests, you can pass `severity-threshold` flag to `snyk test` command with one of the supported options (`low|medium|high`). With this flag, only vulnerabilities of **provided level or higher** will be reported.

```console
$ snyk test --severity-threshold=medium
```

_Note: `low` option currently has the same effect as running without specifying the threshold, i.e. all vulnerabilities will be reported._

### Note for Node.js:
Since `snyk test` looks at the locally installed modules, it needs to run after `npm install` or `yarn install`, and will seamlessly work with `shrinkwrap`, npm enterprise or any other custom installation logic you have.

### Note for Java:
Since `snyk test` looks at the locally installed modules, it needs to run after `mvn install`.

### Note for Scala:
In order to use the CLI to test against your `build.sbt` manifest file, you'll need to first install the <a href="https://github.com/jrudolph/sbt-dependency-graph">sbt-dependency-graph plugin</a>.

Running `snyk test` on your Scala projects without this plugin will throw the following error:

```console
Error: Missing plugin sbt-dependency-graph (https://github.com/jrudolph/sbt-dependency-graph).
Please install it globally or on the current project and try again.
```

### Note for Golang:
Since `snyk test` inspects the locally installed modules, it needs to run after the `vendor/` folder was populated via `dep ensure` or `govendor sync`. In addition, the `GOPATH` environment variable must be set correctly.

### Note for .NET:
Since `snyk test` inspects the locally installed modules, it needs to run after the `packages/`(.NET) or `obj/`(.NET Core) folder has been populated via Visual Studio or `dotnet restore`.

### Note for PHP:
Since `snyk test` inspects the locally installed modules, it needs to run after the `composer.lock` file has been created by `composer install`.

### Test a public GitHub repository
To test a public Github repository, run `snyk test` and include the Github URL to the repo.

```console
$ snyk test https://github.com/snyk/snyk
```
The following git URL formats are supported:

  - git://github.com/user/project.git#commit-ish
  - https://github.com/user/project#commit-ish
  - user/project#commit-ish

This also works for Bitbucket and GitLab.

You can also test a public npm package or Github project [via the Test page on snyk.io](https://snyk.io/test/).

### Test a public npm package
You can also use `snyk test` to **scrutinize a public package before installing it**, to see if it has known vulnerabilities or not. Using the package name will test the latest version of that package, and you can also provide a specific version or range using `snyk test module[@semver-range]`.

```console
snyk test lodash
snyk test ionic@1.6.5
```

### Test a Maven or Gradle project with variables
You can pass variables to `snyk test` running on Maven or Gradle projects. This is useful when you want to test a specific profile (in Maven) or configuration (in Gradle), or pass system properties. This is done by sending flags after a double-dash option when running `snyk test`. Note that all flags after the double-dash option will be used as Maven or Gradle flags.

For example, suppose you want to test a specific Maven profile: `prod`. Running the following will test this profile:
```console
snyk test -- -Pprod
```
In another example, if you use a system property in your pom.xml file, e.g: `<version>${pkg_version}</version>`, you can define the system property in `snyk test` as follows:
```console
snyk test -- -Dpkg_version=1.4
```
For testing a Gradle project with test dependencies, you would be able to pass the appropriate configuration to `snyk test`:
```console
snyk test -- --configuration testCompile
```
