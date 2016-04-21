---
title: Test
---

<p>To only test your project for known vulnerabilities, browse to your project’s folder and run <code>snyk test</code>:</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">cd ~/projects/myproj/</span>
<span class="go">snyk test</span></code></pre></div>

<p><code>snyk test</code> takes stock of all the local dependencies and queries the snyk service for related known vulnerabilities. It displays the found issues along with additional information, and suggests remediation steps. Since <code>snyk test</code> looks at the locally installed modules, it needs to run after <code>npm install</code>, and will seamlessly work with <code>shrinkwrap</code>, npm enterprise or any other custom installation logic you have.</p>

<p><code>snyk test</code> can also get a folder name as an argument, which is especially handy if you want to <strong>test multiple projects.</strong> For instance, the following command tests all the projects under a certain folder for known vulnerabilities:</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">cd ~/projects/</span>
<span class="go">snyk test *</span></code></pre></div>

<p>To address the issues <code>snyk test</code> found, run <a href="#wizard"><code>snyk wizard</code></a>.</p>

<p>You can also use <code>snyk test</code> to <strong>scrutinize a public package before installing it</strong>, to see if it has known vulnerabilities or not. Using the package name will test the latest version of that package, and you can also provide a specific version or range using <code>snyk test module[@semver-range]</code>.</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk test lodash</span>
<span class="go">snyk test ionic@1.6.5</span></code></pre></div>

<p><strong>To test a public Github repository,</strong> run <code>snyk test</code> and include the Github URL to the repo.</p>
<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk test https://github.com/snyk/snyk</span></code></pre></div>
<h3 id="git-url-formats">The following git URL formats are supported:</h3>

<ul>
  <li>git://github.com/user/project.git#commit-ish</li>
  <li>https://github.com/user/project#commit-ish</li>
  <li>user/project#commit-ish</li>
</ul>
<p>This also works for Bitbucket and GitLab.</p>
<p>You can also test a public npm package or Github project <a href="https://snyk.io/test/" title="Test page">via the Test page on snyk.io</a></p>
