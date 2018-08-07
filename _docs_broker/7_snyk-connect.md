---
title: "Connect Snyk to your Brokered SCM"
---

Once your Broker client is up and running, you can connect you Snyk account to your SCM in a secure manner.

 1. **Important:** log out of [https://snyk.io](https://snyk.io)
 2. log back in to [https://snyk.io](https://snyk.io)
 3. select the organisation that you're using with your Broker
 4. navigate to the "Projects" page
 5. click on "Add Projects"
 6. you will be prompted to select the type of SCM - GitHub (for both GitHub.com or GitHub Enterprise) or Bitbucket Server, depending on your organisation's settings
 7. if you choose GitHub, you will be prompted for GitHub.com permissions, which must be provided. This is required while the Broker is in early-access, but this access *is not used*
 8. you should see repositories from your Brokered SCM

### Troubleshooting

If you do not see any repositories, you may need to click the "Refresh results" link.

If you see your GitHub.com repositories then log out, then log back in and try again.
