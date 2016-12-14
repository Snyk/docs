---
title: Test
---
**Test a local project**
<p>To only test your project for known vulnerabilities, browse to your project’s folder and run <code>snyk test</code>:</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">cd ~/projects/myproj/</span>
<span class="go">snyk test</span></code></pre></div>

<p><code>snyk test</code> takes stock of all the local dependencies and queries the snyk service for related known vulnerabilities. It displays the found issues along with additional information. For Node.js projects, it also suggests remediation steps.</p>

<p>When testing locally, you can specify the file that Snyk should inspect for package information.</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">$ snyk test --file=package.json</span>
</code></pre></div>

<p>When ommitted Snyk will try to detect the appropriate file for your project by looking for a <code>package.json</code> or <code>Gemfile</code> file. If both files exist it will use the package.json file. In this case you can force a Ruby test by pointing to your Gemfile.

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go"> $ snyk test --file=Gemfile</span>
</code></pre></div>

<p><code>snyk test</code> can also get a folder name as an argument, which is especially handy if you want to <strong>test multiple projects.</strong> For instance, the following command tests all the projects under a certain folder for known vulnerabilities:</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">cd ~/projects/</span>
<span class="go">snyk test *</span></code></pre></div>

<p>Note for Node.js: <br>
Since <code>snyk test</code> looks at the locally installed modules, it needs to run after <code>npm install</code>, and will seamlessly work with <code>shrinkwrap</code>, npm enterprise or any other custom installation logic you have.</p>

**Test a public GitHub repository**
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

**Test a public npm package**
<p>You can also use <code>snyk test</code> to <strong>scrutinize a public package before installing it</strong>, to see if it has known vulnerabilities or not. Using the package name will test the latest version of that package, and you can also provide a specific version or range using <code>snyk test module[@semver-range]</code>.</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk test lodash</span>
<span class="go">snyk test ionic@1.6.5</span></code></pre></div>
