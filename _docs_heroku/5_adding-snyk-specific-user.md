---
title: Adding a Snyk-specific user to Heroku
---
On Heroku, each user is limited to one API key so we suggest adding a dedicated user for your Snyk org. That way if at some point you need to revoke the key for any reason, you can do so without impacting anyone within your org.

This can be accomplished through the Heroku admin interface, or from the command line using the following command:

```
heroku access:add joe@example.com
```

You can learn more about how to add another user to your application on the [Heroku documentation](https://devcenter.heroku.com/articles/collaborating).
