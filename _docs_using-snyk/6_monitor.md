---
title: Monitor
---

<p>With <a href="#test"><code>test</code></a> and <a href="#protect"><code>protect</code></a>, you’re well set up to address currently known vulnerabilities. However, new vulnerabilities are constantly disclosed - which is where <code>monitor</code> comes in.</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">cd ~/projects/myproject/ snyk monitor</span></code></pre></div>

<p>Before you deploy, run <code>snyk monitor</code> in your project directory. This will take a snapshot of your current dependencies, so we can notify you about newly disclosed vulnerabilities in them, or when a previously unavailable patch or upgrade path are created. If you take multiple snapshots of the same project, we will only alert you to new information about the latest one.</p>

<p>Log in and go to <a href="https://snyk.io/monitor/">snyk.io/monitor</a> to see the lastest snapshot and history of your project.</p>

<div class="screenshot">
<h3 class="screenshot__label">Example output</h3>
<pre class="code">$ snyk monitor
Captured a snapshot of this project's dependencies. Explore this snapshot at https://snyk.io/monitor/1a53f19a-f64f-44ab-b122-74ce82c1c34b
Notifications about newly disclosed vulnerabilities related to these dependencies will be emailed to you.</pre>
</div>
