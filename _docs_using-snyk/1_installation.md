---
title: Installation
---

Snyk is installed via npm. Run these commands to install it for local use:

<div class="highlight"><pre><code class="language-console" data-lang="console">npm install -g snyk</code></pre></div>

Once installed, you need to authenticate with your Snyk account:

<div class="highlight"><pre><code class="language-console" data-lang="console">snyk auth</code></pre></div>

Now you can perform a quick test on a public npm package, for instance:

<div class="highlight"><pre><code class="language-console" data-lang="console">snyk test ionic</code></pre></div>

As you can see, Snyk found and reported several vulnerabilities in the package. For each issue found, Snyk provides the severity of the issue, a link to a detailed description, the path through which the vulnerable module got into your system, and guidance on how to fix the problem.

<div class="screenshot">
<h3 class="screenshot__label">Example output</h3>
<pre class="code">$ snyk test
<span class="syn--red">✗ High severity vulnerability found on minimatch@0.3.0</span>
- desc: Regular Expression Denial of Service
- info: https://snyk.io/vuln/npm:minimatch:20160620
- from: ionic@2.1.17 > gulp@3.8.8 > liftoff@0.12.1 > findup-sync@0.1.3 > glob@3.2.11 > minimatch@0.3.0
<span class="syn--white syn--bold">Upgrade direct dependency gulp@3.8.8 to gulp@3.8.11 (triggers upgrades to liftoff@2.2.0 > findup-sync@0.3.0 > glob@5.0.15 > minimatch@3.0.2)</span>

<span class="syn--red">✗ Medium severity vulnerability found on moment@2.11.1</span>
- desc: Regular Expression Denial of Service
- info: https://snyk.io/vuln/npm:moment:20161019
- from: ionic@2.1.17 > moment@2.11.1
<span class="syn--white syn--bold">Upgrade direct dependency moment@2.11.1 to moment@2.15.2</span>

<span class="syn--red">✗ Medium severity vulnerability found on send@0.10.1</span>
- desc: Root Path Disclosure
- info: https://snyk.io/vuln/npm:send:20151103
- from: ionic@2.1.17 > serve-static@1.7.1 > send@0.10.1
<span class="syn--white syn--bold">Upgrade direct dependency serve-static@1.7.1 to serve-static@1.8.1 (triggers upgrades to send@0.11.1)</span></pre>
</div>
