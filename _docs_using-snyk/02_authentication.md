---
title: Authentication
---

Some Snyk commands require authentication. We use GitHub for authentication, but **do not require access to your repositories**, only your email address. You can authenticate by running `snyk auth` in your terminal, and it'll guide you through this process.

Alternatively, you can visit [your account](https://app.snyk.io/account), copy your token and set the environment variable `SNYK_TOKEN` to your token. This approach is recommended for CI environments.
