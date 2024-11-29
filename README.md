**Welcome to Cloudsmith Support Assessment**

Please review the documentation provided by the recruiter for full instructions.

**Repository Overview**

This repository contains a simple Python package that can be built and published to Cloudsmith using GitHub Actions.

**Setup**

1. Fork the repository to your own GitHub account.
2. Create Github Actions variables for the following:
    - `CLOUDSMITH_NAMESPACE`
    - `CLOUDSMITH_SERVICE_SLUG`
3. Clone the repository to your local machine to start making changes.

**Build and Publish Process**

The process involves three workflows:

### 1. `build_package.yml`

* Triggered by a push or pull request to the main branch.
* Builds a Python package and saves it as an artifact in GitHub Actions.

### 2. `realease_package.yml`

* Triggered by the `build_package.yml` workflow completing successfully.
* Downloads the artifact from GitHub Actions and pushes it to the staging repository on Cloudsmith.

### 3. `promote_package.yml`

* Triggered manually by the repository maintainer.
* Promotes the package from the staging repository to the production repository on Cloudsmith.

**Authentication**

OIDC Authentication is used to authenticate with Cloudsmith.
