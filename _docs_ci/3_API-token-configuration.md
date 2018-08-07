---
title: API token configuration
---

You can find your API token in your [account settings on snyk.io](https://app.snyk.io/account/). 
Make sure you don't check your API token into source control, to avoid exposing it to others. Instead, use your CI environment variables to configure it.

See guidance for how to do this on:

* [Travis](https://docs.travis-ci.com/user/environment-variables/)
* [Circle](https://circleci.com/docs/environment-variables/)
* [Codeship](https://codeship.com/documentation/continuous-integration/set-environment-variables/)

You can find others through an easy [Google search]( https://www.google.co.uk/webhp?sourceid=chrome-instant&ion=1&espv=2&ie=UTF-8#q=setting+up+env+variables+in+CI).
