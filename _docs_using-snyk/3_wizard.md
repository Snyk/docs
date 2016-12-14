---
title: Wizard
---

<p>Snyk’s <code>wizard</code> walks you through finding and fixing the known vulnerabilities in your project. Note that the wizard is currently <strong>only available for Node.js projects.</strong></p>

<p>It leverages the separate <a href="#test"><code>test</code></a>, <a href="#protect"><code>protect</code></a> and <a href="#monitor"><code>monitor</code></a> actions, supported by an interactive workflow. To run the wizard, navigate to your project folder and run <code>snyk wizard</code> like so:</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">cd ~/projects/myproj/</span>
<span class="go">snyk wizard</span></code></pre></div>

<p>The wizard goes through multiple phases.
First, it takes stock of which dependencies are locally installed, queries the snyk service for related known vulnerabilities, and asks you how you want to address each vulnerability that was found. As you answer the questions, the wizard will create a Snyk policy file, stored in a file named <code>.snyk</code>, which will guide future Snyk commands.</p>

<p>Here are the possible remediation steps for each vulnerability:</p>

<ul>
  <li><strong>Upgrade</strong> - if upgrading a direct dependency can fix the current vulnerability, the wizard can automatically modify your <code>package.json</code> file to use the newer version and run <code>npm update</code> to apply the changes.</li>
  <li><strong>Patch</strong> - Sometimes there is no direct upgrade that can address the vulnerability, or there is one but you can’t upgrade due to functional reasons (e.g. it’s a major breaking change). For such cases, the wizard lets you patch the issue (using patches the Snyk team created and maintain). This option will make the minimal modifications to your locally installed module files to fix the vulnerability. It will also update the policy to patch this issue when running <a href="#protect"><code>snyk protect</code></a>, as shown below.</li>
  <li><strong>Ignore</strong> - If you believe this vulnerability is not exploitable, you can set the Snyk policy to ignore this vulnerability. By default, we will ignore the vulnerability for 30 days, to avoid easily hiding a true issue. If you want to ignore it permanently, you can manually edit the generated <code>.snyk</code> file. If neither a patch nor an upgrade are available, you can choose to ignore the issue for now, and we’ll notify you when a new patch or upgrade is available.</li>
</ul>

<p>If more than one vulnerability is introduced via the same module, then the wizard groups them. You can upgrade, patch or ignore all of them; or if you want to see more details, you can review each vulnerability separately.</p>

<div class="screenshot">
<h3 class="screenshot__label">Example output</h3>
<pre class="code">$ snyk wizard

Snyk's wizard will:

  * Enumerate your local dependencies and query Snyk's servers for vulnerabilities
  * Guide you through fixing found vulnerabilities
  * Create a .snyk policy file to guide snyk commands such as test and protect
  * Remember your dependencies to alert you when new vulnerabilities are disclosed
 
 Note: Node.js only. 

Loading dependencies...
Querying vulnerabilities database...
Tested 446 dependencies for known vulnerabilities, <span class="syn--red syn--bold">found 8 vulnerabilities, 20 vulnerable paths.</span>

<span class="syn--green">?</span> <span class="syn--white syn--bold">High severity vuln found in tough-cookie@2.2.2, introduced via azure-mgmt-storage@0.9.16
- desc: ReDoS via long string of semicolons
- info: <a href="https://snyk.io/vuln/npm:tough-cookie:20160722" title="Vulnerability report.">https://snyk.io/vuln/npm:tough-cookie:20160722</a>
- from: azure-mgmt-storage@0.9.16 > azure-common@0.9.11 > request@2.45.0 > tough-cookie@2.2.2</span> <span class="syn--blue">Upgrade</span>

<span class="syn--green">?</span> <span class="syn--white syn--bold">6 vulnerabilities introduced via falcor-router-demo@1.0.5
  - info: <a href="https://snyk.io/package/npm/falcor-router-demo/1.0.5" title="Package test report.">https://snyk.io/package/npm/falcor-router-demo/1.0.5</a>
  Remediation options (Use arrow keys)</span>
<span class="syn--blue">❯ Re-install falcor-router-demo@1.0.5 (triggers upgrade to minimatch@3.0.2, tough-cookie@2.3.0) </span>
  Review vulnerabilities separately
  Set to ignore for 30 days (updates policy)
  Skip</pre>
</div>

<p>Once all the issues are addressed, <code>snyk wizard</code> will optionally integrate some tests and protection steps into your <code>package.json</code> file:
<ul>
	<li>It can add <a href="#test"><code>snyk test</code></a> to the <code>test</code> script, which will query your local dependencies for vulnerabilities and err if found (except those you chose to ignore).</li>
	<li>If you chose to patch an issue, the wizard will optionally add <a href="#protect"><code>snyk protect</code></a> to your project as a <code>post-install</code> step. This is helpful if you publish this module, as it will repeatedly patch the issues specified in <code>.snyk</code> every time a module is installed.</p></li>
</ul>

<p>Lastly, the wizard will create the <code>.snyk</code> file, modify <code>package.json</code> and run <code>npm update</code> to apply the changes. To monitor your project for new vulnerabilities, the wizard takes a snapshot of your current dependencies (similar to running <a href="#monitor"><code>snyk monitor</code></a>). You can see all the snapshots for a project on the snyk website. We'll notify you via email if you're affected by newly disclosed vulnerabilities in them, or when a previously unavailable patch or upgrade path are available.</p>

<h3 id="a-few-things-to-note">A few things to note:</h3>

<ul>
  <li>The wizard doesn’t perform any git (or source control) actions, so be sure to add the <code>.snyk</code> file to your repository.</li>
  <li>Subsequent runs of the wizard will not show items previously ignored. To start a-fresh, run <code>snyk wizard --ignore-policy</code>.</li>
  <li>By default, both <code>wizard</code> and <a href="#test"><code>test</code></a> ignore devDependencies. To test those, add the <code>--dev</code> flag.</li>
</ul>
