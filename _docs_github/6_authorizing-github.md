---
title: Authorizing GitHub
---
### Repository access

When granting Snyk access to GitHub, you can choose to:

* grant access to public and private repositories
* grant access to public repositories only

This is for all GitHub organisations you have sufficient permissions for.

Note that granting access will test your repositories for vulnerabilities only once - it won't automatically set webhooks or enable continuous monitoring.

![Repo access permissions](https://res.cloudinary.com/snyk/image/upload/c_scale,h_358/v1482163908/docs/GH_repository_access.png)

### GitHub organisations

To test your GitHub organisation's repositories with Snyk, you will need to have sufficient user permissions. When you authenticate Snyk, GitHub will show you which organisations you can integrate.

If you do not have the correct permissions, you will see "Access request pending" next to your ogranisation's name, and you will be unable to see this organisation's projects in Snyk.

![Adding your GH repos](https://res.cloudinary.com/snyk/image/upload/f_auto,q_auto,w_auto/v1479811749/docs/github-org-permissions.png)

If you'd like to integrate this organisation, you will need to [request organisational approval](https://help.github.com/articles/requesting-organization-approval-for-your-authorized-applications/) in GitHub.
