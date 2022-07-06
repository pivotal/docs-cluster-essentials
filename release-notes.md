# Release notes

This topic contains release notes for Cluster Essentials for VMware Tanzu. A new minor release for Cluster Essentials is publish every quarter. Monthly patch releases are published to address critical bugs and CVEs, if there are any.

## <a id='1-2'></a> v1.2.0

**Release Date**: July 6, 2022

### <a id='1-2-new-features'></a> New features

* Updating **kapp-controller to v0.38.3**. Some highlights from this release are listed below. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).
  * Add support for Kubernetes 1.24
  * PackageRepositories support having identical packages from multiple different repositories
  * Remove support for Helm v2
  * kapp-controller will now wait indefinitely for APIService resource to succeed
  * kapp-controller will now keep a maximum of 5 app changes by default

* Updating **secretgen-controller to v0.9.1**
  * SecretTemplate API: SecretTemplate resources introduce a highly flexible way of telling secretgen-controller to populate a single secret from fields in any other resource on the cluster selected via JSONpath.


## <a id='1-1'></a> v1.1.0

**Release Date**: April 5, 2022

### <a id='1-1-new-features'></a> New features

* Updating **kapp-controller to v0.34.0**. This update brings in significant performance improvements when running large Package Repositories. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).

* Updating **secretgen-controller to v0.8.0**
