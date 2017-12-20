---
title: Protect
---

<p>The <code>protect</code> command applies the patches specified in your <code>.snyk</code> file to the local file system. This is currently supported for <strong>Node.js projects only.</strong></p>
<p>Run <code>snyk protect</code> after you’ve created a .snyk file and installed your local dependencies (e.g. by running <code>npm install</code> or <code>yarn install</code>).<code>snyk wizard</code> will do this as a last step.</p>

<p>Since running <code>protect</code> is the way to repeatedly apply patches, you should run it every time you reinstall your modules. Common integration points would be your CI/build system, your deployment system, and adding it as a post installation step in your <code>package.json</code> file (necessary if you consume this module via <code>npm</code> or <code>yarn</code>).</p>
