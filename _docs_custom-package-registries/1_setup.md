---
title: Setup
---
If authentication is required to access your custom registry you will need to first configure the Artifactory package repository integration.

To configure the Artifactory integration go to Integrations > Artifactory and click ‘Connect to Artifactory’ and complete the fields - url to your Artifactory, username and password.

Once the integration is set up you can configure Maven settings by navigating to Settings > Languages > Java

You can choose whether to use Artifactory as a mirror or as an additional repository where your artifacts will reside.  These settings will be very similar to what you have in ~/.m2/settings.xml.


