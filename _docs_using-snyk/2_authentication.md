---
title: Authentication
---

Some Snyk commands require authentication. We use GitHub for authentication, but **do not require access to your repositories**, only your email address. You can authenticate by clicking [“Sign Up”](https://snyk.io/auth/github), and pasting in the lines from your dashboard, which look roughly like this:

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk auth &lt;your token&gt;</span></code></pre></div>

Alternatively, you can run `snyk auth` in your terminal and it’ll guide you through this process.
