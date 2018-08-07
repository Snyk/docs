---
title: Troubleshooting
---

If your instance of the Snyk CLI has started failing, follow these steps to resolve:

1. Ensure you are on the most up to date version of the CLI by running

   ```bash
   npm install -g snyk
   ```
2. Make sure you are authenticating prior to running the Snyk CLI command
   You can either authenticate by running `snyk auth` in your terminal, and it’ll guide you through this process, or visit [your account](https://app.snyk.io/account), copy your API token and set the environment variable `SNYK_TOKEN` to your token.

3. If you are still having problems after upgrading and authenticating send an email to [support@snyk.io](mailto:support@snyk.io) and we will help you out.

### Note:

Authentication is required for `snyk test` and `snyk monitor` from Tuesday the 24th of January 2017 for details on why we require authentication take a look at our blog post [Requiring authentication in Snyk CLI](https://snyk.io/blog/requiring-authentication/).

Registration with Snyk is free. If you do not already have an account all you need to do is run `snyk auth` in your terminal (or [sign up](https://app.snyk.io/signup)) to get an account setup.
