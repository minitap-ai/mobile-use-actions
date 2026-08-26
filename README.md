# mobile-use-actions

Public GitHub Actions required by the [`mobile-use`](https://github.com/minitap-ai/mobile-use) release workflow.

The private `minitap-ai/devops-common` repository is the source of truth. This repository contains reviewed public snapshots only; changes are copied deliberately when `mobile-use` needs them.

## Actions

- `check-tag-version`
- `dockerhub-build-push`
- `gcp-docker-build-push`
- `gcp-container-vulnerability-scan`

Consumers should pin actions to a full commit SHA.

The GCP build action exposes the pushed image's immutable `digest` and `image-uri`. The vulnerability scanner accepts one or more newline-separated immutable image URIs, publishes a GitHub summary and raw findings artifact, and optionally alerts Slack for HIGH/CRITICAL findings or scanner failures. Findings and scanner failures never block a release.
