---
title: Monitor
---

<p>With <a href="#test"><code>test</code></a> and <a href="#protect"><code>protect</code></a>, you’re well set up to address currently known vulnerabilities. However, new vulnerabilities are constantly disclosed - which is where <code>monitor</code> comes in.</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">cd ~/projects/myproject/</span>
<span class="go">snyk monitor</span></code></pre></div>

<p>Just before you deploy, run <code>snyk monitor</code> in your project directory. This will take a snapshot of your current dependencies, so we can notify you about newly disclosed vulnerabilities in them, or when a previously unavailable patch or upgrade path is created. If you take multiple snapshots of the same project, we will only alert you to new information about the latest one.</p>

<p>Log in and go to <a href="https://app.snyk.io/monitor/">snyk.io/monitor</a> to see the latest snapshot and history of your project.</p>

<div class="screenshot">
<h3 class="screenshot__label">Example output</h3>
<pre><code>$ snyk monitor
Captured a snapshot of this project's dependencies. Explore this snapshot at https://app.snyk.io/monitor/1a53f19a-f64f-44ab-b122-74ce82c1c34b
Notifications about newly disclosed vulnerabilities related to these dependencies will be emailed to you.</code></pre>
</div>

<h3>Specifying which organisation for monitoring</h3>
<p>If you have several <a href="https://snyk.io/docs/orgs">organisations set up in Snyk</a>, running <code>snyk monitor</code> will associate the generated snapshot to your "default" (personal) org. To specify a different organisation, you can use the <code>--org</code> option.</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk monitor --org=my-org-name</span></code></pre></div>

<h3>Overriding the project name</h3>
<p>If you do not wish to have the name of your project uploaded to Snyk you can specify a name to override it with. You can also use this flag when you are testing multiple manifest files within the same project and need to differentiate between them.</p>

<p>Valid project names can contain: letters, digits, slashes, underscores, periods and dashes. Monitor will fail and will output a message that an invalid name was provided if the project name is not valid.</p>

<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">
snyk monitor --file=package.json --project-name=myapp-frontend
<br />snyk monitor --file=build.sbt --project-name=myapp-backend </span></code></pre></div>

<h3>Monitor a Maven or Gradle project with variables</h3>
<p>You can pass variables to <code>snyk monitor</code> running on Maven or Gradle projects. This is useful when you want to monitor a specific profile (in Maven) or configuration (in Gradle), or pass system properties. This is done by sending flags after a double-dash option when running <code>snyk monitor</code>. Note that all flags after the double-dash option will be used as Maven flags.</p>
<p>For example, suppose you want to monitor a specific Maven profile: <code>prod</code>. Running the following will monitor this profile:</p>
<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk monitor -- -Pprod</span></code></pre></div>
<p>In another example, if you use a system property in your pom.xml file, e.g: <code>&lt;version&gt;${pkg_version}&lt;/version&gt;</code>, you can define the system property in <code>snyk monitor</code> as follows:
<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk monitor -- -Dpkg_version=1.4</span></code></pre></div>
<p>For monitoring a Gradle project with test dependencies, you would be able to pass the appropriate configuration to <code>snyk monitor</code>:
<div class="highlight"><pre><code class="language-console" data-lang="console"><span class="go">snyk monitor -- --configuration testCompile</span></code></pre></div>
