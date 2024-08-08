# Cluster Essentials Release notes

This topic contains release notes for Cluster Essentials for VMware Tanzu. A new minor release for Cluster Essentials is publish every quarter. Monthly patch releases are published to address critical bugs and CVEs, if there are any.

## <a id='1-10'></a> v1.10.0

**Release Date**: 09 August 2024

### <a id='1-10-new-features'></a> New features

- Adds partial support for Downward API with the kctrl package release.

- Adds defaults for the version flag while installing packages using kctrl.

- Adds the ability to force HTTP Basic when fetching from Git repos.

- Updates **kapp-controller to v0.53.0**. For a full list of new features, see the
  [kapp-controller release notes](https://github.com/carvel-dev/kapp-controller/releases/tag/v0.53.0).

- Updates **secretgen-controller to v0.18.0**. For a full list of new features, see the
  [secretgen-controller release notes](https://github.com/carvel-dev/secretgen-controller/releases/tag/v0.18.0).

- Updates Carvel CLIs:
    - imgpkg to v0.43.0. See the [imgpkg release notes](https://github.com/carvel-dev/imgpkg/releases/tag/v0.43.0).
    - kapp to v0.63.2. See the [kapp release notes](https://github.com/carvel-dev/kapp/releases/tag/v0.63.1).
    - kbld to v0.44.0. See the [kbld release notes](https://github.com/carvel-dev/kbld/releases/tag/v0.44.0).
    - ytt to v0.50.0. See the [ytt release notes](https://github.com/carvel-dev/ytt/releases/tag/v0.50.0).
