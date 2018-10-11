---
title: Copying settings, integrations and policies to a new org
---

Group admins have the ability to copy org settings from an existing org to a new one, so that integrations, policies and settings that are the same for multiple orgs can be set up once and copied across to newly created orgs. This is possible [via our API](https://snyk.docs.apiary.io/#reference/groups/organisations-in-groups/create-a-new-organisation-in-the-group), or in the UI.

![Creating a new grouped org screen with copy settings.](https://res.cloudinary.com/snyk/image/upload/c_scale,w_834/v1539259823/docs/groups/new-org-copy-settings.png)

Under the heading “copy across all settings and integrations”, there is a dropdown containing a list of all orgs within your group. By default, it is set to “do not copy”, and will not copy any settings across. Selecting an org will clone all settings from that org to the one you’re creating.

The settings that are copied across will include any integrations you have set up in that org, license policies, ignore policies, and language settings. This action will not copy across members, service accounts, projects, or notification preferences.

Note that copying across settings from an org will _not_ keep the copied settings in sync between orgs. For example, if you change the license policy in the cloned org, these changes will not be reflected in the original org. After the creation stage, they are treated as completely separate entities.
