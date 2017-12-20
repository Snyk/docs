---
title: Ignore
---

<p>Sometimes, Snyk may alert you to a vulnerability that you either has no patches or updates available, or that you do not believe to be currently exploitable in your application. In this case, you may want to tell Snyk to ignore the vulnerability for a certain period of time.</p>

<p>If you're using <code>snyk wizard</code> (<strong>only available on Node.js projects</strong>), the wizard will give you the option of ignoring the vulnerability for a period of 30 days. If you're using Ruby or Java, or if you want to specify a different duration, you can use the <code>snyk ignore</code> command.</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk ignore --id=IssueID [--expiry=expiry] [--reason='reason for ignoring']</span></code></pre></div>

### Options

`snyk ignore` accepts three options:

<table>
  <thead>
    <tr>
      <th>Option</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>--id</code></td>
      <td><p>The Snyk ID for the issue to ignore. Found by running <code>snyk test</code> and grabbing the last segment of the URL for a given vulnerability.</p>

      <p><strong>Example:</strong> For the vulnerability found at <a href="https://snyk.io/vuln/npm:tough-cookie:20160722">https://snyk.io/vuln/npm:tough-cookie:20160722</a>, you would use:<br/> <code>--id=npm:tough-cookie:20160722</code></p></td>
      <td>None</td>
      <td><strong>Yes</strong></td>
    </tr>
    <tr>
      <td><code><span style="white-space: nowrap;">--expiry</span></code></td>
      <td><p>The expiry date string, according to <a href="https://tools.ietf.org/html/rfc2822#page-14">RFC2822</a>.</p>

      <p><strong>Example:</strong> <code>--expiry=2017-04-30</code></p></td>
      <td>30 days</td>
      <td>No</td>
    </tr>
    <tr>
      <td><code>--reason</code></td>
      <td><p>The reason for ignoring the issue.</p>

      <p><strong>Example:</strong> <code>--reason='Not currently exploitable.'</code></p></td>
      <td>"None Given"</td>
      <td>No</td>
    </tr>
  </tbody>
</table>