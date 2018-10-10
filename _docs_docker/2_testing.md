---
title: "Testing Docker images"
---

We scan Docker images by extracting the image layers and inspecting the package manager manifest info. We then compare every OS package installed in the image against our [Docker vulnerability database](/vuln?type=linux).

To test an image, make sure it is pulled locally (i.e. `docker pull ubuntu:latest`).
* Run `snyk test --docker ubuntu:latest` to test the image for vulnerabilities.
* Run `snyk test --docker myapp:latest —file=./myapp/Dockerfile` to test the image for vulnerabilities, and get a more detailed remediation advice for your image by passing the local Dockerfile.
* Run `snyk monitor --docker ubuntu:latest` to create a snapshot of the image's dependencies for continuous monitoring.
