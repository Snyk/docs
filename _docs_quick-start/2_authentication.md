---
title: Authentication
---

If this is the first time you use Snyk, the wizard will first ask you to register using your GitHub account. *Note that Snyk does not require access to your repositories*. It only requests access to your email, using GitHub as an authentication system.

```console
snyk wizard

Now redirecting you to our GitHub auth page, go ahead and log in,
and once the auth is complete, return to this prompt and you’ll
be ready to start using snyk.

If you can’t wait use this url:
https://snyk.io/login?token=9b4ae29b-d430-4d79-b9a3-dd522e77f8b9

Waiting...
```

Once authenticated, the wizard will get an API token to store locally and get on with the testing. The same authentication process can be done by running `snyk auth`, or setting the environment variable `SNYK_TOKEN` to your API token. You can find your API token in your [account settings on snyk.io](https://snyk.io/account/).
