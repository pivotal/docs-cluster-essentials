# Cluster Essentials Release notes

This topic contains release notes for Cluster Essentials for VMware Tanzu. A new minor release for Cluster Essentials is publish every quarter. Monthly patch releases are published to address critical bugs and CVEs, if there are any.

## <a id='1-9'></a> v1.9.0

**Release Date**: April 30, 2024

### <a id='1-9-new-features'></a> New features

- Enables the use of `--diff-anchored` with kapp.

- Considers path nestedness for all possible downward API values.

- Adds the ability to force HTTP Basic when fetching from git repos.

- Updates **kapp-controller to v0.51.0**. For a full list of new features, see the
  [kapp-controller release notes](https://github.com/carvel-dev/kapp-controller/releases/tag/v0.51.0).

- Updates **secretgen-controller to v0.17.2**. For a full list of new features, see the
  [secretgen-controller release notes](https://github.com/carvel-dev/secretgen-controller/releases/tag/v0.17.2).

- Updates Carvel CLIs:
    * imgpkg to v0.42.0. See the [imgpkg release notes](https://github.com/carvel-dev/imgpkg/releases/tag/v0.42.0).
    * kapp to v0.62.0. See the [kapp release notes](https://github.com/carvel-dev/kapp/releases/tag/v0.62.0).
    * kbld to v0.43.0.
    * ytt to v0.49.0.
