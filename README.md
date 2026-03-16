# Baserow Helm Repository

This repository contains Helm charts for deploying Baserow, an open-source no-code database platform, on Kubernetes clusters.

# Updating the Charts

This repository updates automatically on new Baserow releases. When triggered, the Baserow repository creates a Helm chart build and triggers the workflow in this repository. The workflow then downloads the built chart artifact and publishes it to GitHub Pages and the Artifact Hub registry.

