---
title: "Testing Docker images"
---

We scan Docker images by extracting the image layers and inspecting the package manager manifest info. We then compare every OS package installed in the image against our [Docker vulnerability database](/vuln?type=linux).

To test an image, make sure it is built (i.e. `docker build -t myapp:mytag .`) or pulled locally (i.e. `docker pull myapp:mytag`).
* Run `snyk test --docker myapp:mytag` to test the image for vulnerabilities.
* Run `snyk test --docker myapp:mytag --file=path/to/Dockerfile` to test the image for vulnerabilities and get remediation advice for the base image of your Dockerfile.
* Run `snyk monitor --docker ubuntu:latest` to create a snapshot of the image's dependencies for continuous monitoring.
