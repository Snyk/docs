---
title: Open Source Packages Disclosure policy
---

We at snyk value the security community and believe that responsible disclosure of security vulnerabilities in open source packages helps us ensure the security and privacy of the users.
​
A responsible disclosure program includes a policy with clear and simple rules of engagement for security researchers to report vulnerabilities they discover. It protects both the developer and researcher, while allowing developers to safely benefit from vulnerabilities discovered by researchers.
​
Security vulnerabilities can be reported to us, and we will manage the responsible disclosure procedure, (1) receiving the report, (2) notifying the developer, (3) coordinating the fix and (4) publicly disclosing the vulnerability giving full credit to the researcher.

### 1. Report

Receiving the submitted vulnerability report from the researcher/reporter, sent to [report@snyk.io](mailto:report@snyk.io).
Snyk will verify and document each reported vulnerability prior to developer notification.

### 2. Developer Notification

The first phase of the public disclosure process, with a goal to provide vulnerability details necessary for the developer to begin their internal resolution process.

If the developer has not acknowledged receipt within 30 business days of the original notification, Snyk will retransmit the vulnerability details to the original contact and at least one secondary contact, if a secondary contact is publicly available. If the developer allows an additional ten business days to elapse following the second notification (40 business days since original notification) without acknowledging the information, vulnerability details will be re-sent not only to the previous two contacts, but also to customers or other stakeholders at Snyk's discretion.

If the product developer does not respond to any of the three notification attempts within an additional ten days following the third notification (50 business days since original notification), or if the developer indicates they do not wish to coordinate disclosure, Snyk may elect to issue a public advisory (Step 4).

Acknowledgement of the notification by the developer should include all of the following items:

a. developer confirms the vulnerability information is received and the schedule for investigation.  
b. developer provides a point of contact responsible for coordinating and tracking information on the issue from within their org.  
c. developer provides an estimate as to when they expect to complete their initial investigation of the security issue provided in the notification.  

### 3. Developer Coordination

Upon successful acknowledgement of the notification, Snyk will work with the developer to determine how the security issue will be addressed. The following tasks are included within this phase:

a. At developer's request, Snyk will provide additional information to assist in the development of a solution.  
b. At developer's request, Snyk may review proposed solutions for effectiveness.  
c. The developer and Snyk will exchange proposed timing for public disclosure of the issue and related solution for mutual approval.  
​
If developer responses to all communications in this phase are not received within ten business days, Snyk may move directly to the Public Disclosure phase.

### 4. Public disclosure

Public Disclosure is the final phase of the disclosure process. During this phase, Snyk's intent is to add the vulnerability to its [public database (vulndb)](https://snyk.io/vuln/), provide information on the vulnerability and related solutions. Public Disclosure may be initiated either by completing the Developer Coordination phase or through a process failure in prior phases.

During the Public Disclosure phase Snyk, and optimally the developer, will disseminate information on the vulnerability and related solution to the public. Snyk may disseminate information through public e-mail lists, web pages or any other medium it deems appropriate to reach the intended audiences.

### 5. PGP Key

As mentioned above, you can report issues simply by emailing us at [report@snyk.io](mailto:report@snyk.io), and a member of the Snyk team will review your confidential report.

If possible, we recommend you encrypt such vulnerability disclosures using the following PGP key:

``` language-markup
-----BEGIN PGP PUBLIC KEY BLOCK-----
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
V7JD6Yv5YR5K0Wf9MsSHZA==
=6Uz+
-----END PGP PUBLIC KEY BLOCK-----
```
