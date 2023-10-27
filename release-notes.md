# Cluster Essentials Release notes

This topic contains release notes for Cluster Essentials for VMware Tanzu. A new minor release for Cluster Essentials is publish every quarter. Monthly patch releases are published to address critical bugs and CVEs, if there are any.

## <a id='1-3-5'></a> v1.3.5

**Release Date**: October 31, 2023

### <a id='1-3-5-resolved-issues'></a> Resolved issues

* Updating **kapp-controller to v0.41.11**. This patch release addresses issues identified in v1.3.4. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.41.11).
* Updating **secretgen-controller to v0.11.8**
* Updating Carvel CLIs
  * imgpkg to v0.31.7
  * kbld to v0.35.6
  * ytt to v0.43.6
  * kapp to v0.53.11

## <a id='1-3-4'></a> v1.3.4

**Release Date**: October 3, 2023

### <a id='1-3-4-resolved-issues'></a> Resolved issues

* Updating **kapp-controller to v0.41.10_vmware.2**. This patch release addresses issues identified in v1.3.3.

## <a id='1-3-3'></a> v1.3.3

**Release Date**: August 31, 2023

### <a id='1-3-3-resolved-issues'></a> Resolved issues

* Updating **kapp-controller to v0.41.10**. This patch release addresses issues identified in v1.3.2. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.41.10).
* Updating **secretgen-controller to v0.11.7**
* Updating Carvel CLIs
  * imgpkg to v0.31.6
  * kbld to v0.35.5
  * ytt to v0.43.5
  * kapp to v0.53.10

## <a id='1-3-2'></a> v1.3.2

**Release Date**: July 31, 2023

### <a id='1-3-2-resolved-issues'></a> Resolved issues

* Updating **kapp-controller to v0.41.9**. This patch release addresses issues identified in v1.3.1. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.41.9).

## <a id='1-3-1'></a> v1.3.1

**Release Date**: June 30, 2023

### <a id='1-3-1-resolved-issues'></a> Resolved issues

* Updating **kapp-controller to v0.41.8**. This patch release addresses issues identified in v1.3.0. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.41.8).
* Updating **secretgen-controller to v0.11.6**
* Updating Carvel CLIs
  * imgpkg to v0.31.5
  * kbld to v0.35.4
  * ytt to v0.43.4
  * kapp to v0.53.8

## <a id='1-3'></a> v1.3.0

**Release Date**: October 7, 2022

### <a id='1-3-new-features'></a> New features

* Adding support for Red Hat OpenShift Container Platform 4.10 running on vSphere and baremetal
* Adding a Windows installer for Cluster Essentials

* Updating **kapp-controller to v0.41.2**. Some highlights from this release are listed below. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).
  * Surface namespace and group-kind of App CR associated resources in App CR status
  * Package authors can now specify that their package can be installed on a certain versions of kapp-controller or Kubernetes
  * Allow configuring minimum app sync period
  * Adjust default TLS cipher suites to be restrictive
  * [Bug fix] Clean up sidecarexec socket file in case of previous unclean process termination

* Updating **secretgen-controller to v0.11.0**

* Updating Carvel CLIs
  * imgpkg to v0.31.0
  * kbld to v0.35.0 
  * ytt to v0.43.0 
  * kapp to v0.53.0
