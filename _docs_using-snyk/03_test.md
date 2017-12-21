---
title: Test
---
<h3>Test a local project</h3>
<p>To only test your project for known vulnerabilities, browse to your project’s folder and run <code>snyk test</code>:</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">cd ~/projects/myproj/</span>
<span class="go">snyk test</span></code></pre></div>

<p><code>snyk test</code> takes stock of all the local dependencies and queries the snyk service for related known vulnerabilities. It displays the found issues along with additional information. For Node.js projects, it also suggests remediation steps.</p>

<p>When <code>snyk test</code> runs, it tries to detect the appropriate file for your project by looking for the following files, in this order:</p>
<ol>
  <li>yarn.lock</li>
  <li>package.json</li>
  <li>Gemfile</li>
  <li>Gemfile.lock</li>
  <li>pom.xml</li>
  <li>requirements.txt</li>
  <li>build.gradle</li>
  <li>build.sbt</li>
  <li>Gopkg.lock</li>
  <li>vendor/vendor.json</li>
  <li>obj/project.assets.json</li>
  <li>*.csproj</li>
</ol>

<p>When testing locally, you can specify the file that Snyk should inspect for package information.</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">$ snyk test --file=package.json</span>
</code></pre></div>

<h3>Note for Node.js:</h3>
<p>Since <code>snyk test</code> looks at the locally installed modules, it needs to run after <code>npm install</code> or <code>yarn install</code>, and will seamlessly work with <code>shrinkwrap</code>, npm enterprise or any other custom installation logic you have.</p>

<h3>Note for Java:</h3>
<p>Since <code>snyk test</code> looks at the locally installed modules, it needs to run after <code>mvn install</code>.</p>

<h3>Note for Scala:</h3>
<p>In order to use the CLI to test against your <code>build.sbt</code> manifest file, you'll need to first install the [sbt-dependency-graph plugin](https://github.com/jrudolph/sbt-dependency-graph).</p>

<p>Running <code>snyk test</code> on your Scala projects without this plugin will throw the following error:</p>

<pre><code>Error: Missing plugin `sbt-dependency-graph` (https://github.com/jrudolph/sbt-dependency-graph).
Please install it globally or on the current project and try again.
</code></pre>

<h3>Note for Golang:</h3>
<p>Since <code>snyk test</code> looks at the locally installed modules, it needs to run after the <code>vendor/</code> was populated via <code>dep ensure</code> or <code>govendor sync</code>. In addition, the <code>GOPATH</code> environment variable must be set correctly.</p>

<h3>Note for .NET:</h3>
<p>Since <code>snyk test</code> looks at the locally installed modules, it needs to run after the <code>packages/</code>(.NET) or <code>obj/</code>(.NET Core) folder has been populated via Visual Studio or <code>dotnet restore</code>.</p>

<h3>Test a public GitHub repository</h3>
<p>To test a public Github repository, run <code>snyk test</code> and include the Github URL to the repo.</p>
<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk test https://github.com/snyk/snyk</span></code></pre></div>
<p>The following git URL formats are supported:</p>

<ul>
  <li>git://github.com/user/project.git#commit-ish</li>
  <li>https://github.com/user/project#commit-ish</li>
  <li>user/project#commit-ish</li>
</ul>
<p>This also works for Bitbucket and GitLab.</p>
<p>You can also test a public npm package or Github project <a href="https://snyk.io/test/" title="Test page">via the Test page on snyk.io.</a></p>

<h3>Test a public npm package</h3>
<p>You can also use <code>snyk test</code> to <strong>scrutinize a public package before installing it</strong>, to see if it has known vulnerabilities or not. Using the package name will test the latest version of that package, and you can also provide a specific version or range using <code>snyk test module[@semver-range]</code>.</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk test lodash</span>
<span class="go">snyk test ionic@1.6.5</span></code></pre></div>

<h3>Test a Maven or Gradle project with variables</h3>
<p>You can pass variables to <code>snyk test</code> running on Maven or Gradle projects. This is useful when you want to test a specific profile (in Maven) or configuration (in Gradle), or pass system properties. This is done by sending flags after a double-dash option when running <code>snyk test</code>. Note that all flags after the double-dash option will be used as Maven or Gradle flags.</p>
<p>For example, suppose you want to test a specific Maven profile: <code>prod</code>. Running the following will test this profile:</p>
<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk test -- -Pprod</span></code></pre></div>
<p>In another example, if you use a system property in your pom.xml file, e.g: <code>&lt;version&gt;${pkg_version}&lt;/version&gt;</code>, you can define the system property in <code>snyk test</code> as follows:
<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk test -- -Dpkg_version=1.4</span></code></pre></div>
<p>For testing a Gradle project with test dependencies, you would be able to pass the appropriate configuration to <code>snyk test</code>:
<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk test -- --configuration testCompile</span></code></pre></div>
