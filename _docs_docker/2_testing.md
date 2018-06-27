---
title: "Testing Docker images"
---

We scan Docker images by extracting the image layers and inspecting the package manager manifest info. We then compare every OS package installed in the image against our [Docker vulnerability database](/vuln?type=linux).
