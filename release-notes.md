# Release notes

This topic contains release notes for Cluster Essentials for VMware Tanzu. A new minor release for Cluster Essentials is publish every quarter. Monthly patch releases are published to address critical bugs and CVEs, if there are any.

## <a id='1-4'></a> v1.5.0

**Release Date**: 

### <a id='1-5-new-features'></a> New features


## <a id='1-4'></a> v1.4.0

**Release Date**: January 9, 2023

### <a id='1-4-issues'></a> Known Issues
* Automatic IaaS authentication for fetching images from IaaS provided registry, for exmaple, ECR from EKS, does not succeed. 
VMware recommends continued use of Cluster Essentials v1.3.0 if this feature is required.

### <a id='1-4-new-features'></a> New features
* Adding support for Kubernetes 1.25 and OpenShift 4.11
* Updating **kapp-controller to v0.44.1**. Some highlights from this release are listed below. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).
  * Caching of images and bundles to improve resiliency when the image registry is not available
  * Improved experience deploying on OpenShift 4.11 by resolving warnings
  * Improved pausing and waiting behaviors for PackageInstall
* Updating **secretgen-controller to v0.13.0**
* Updating Carvel CLIs
  * imgpkg to v0.31.1
  * kapp to v0.54.1
  * kbld to v0.36.1
  * ytt to v0.44.1

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
  
## <a id='1-2'></a> v1.2.0

**Release Date**: July 11, 2022

### <a id='1-2-new-features'></a> New features

* Updating **kapp-controller to v0.38.4**. Some highlights from this release are listed below. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).
  * Add support for Kubernetes 1.24
  * PackageRepositories support having identical packages from multiple different repositories
  * Remove support for Helm v2
  * kapp-controller will now wait indefinitely for APIService resource to succeed
  * kapp-controller will now keep a maximum of 5 app changes by default

* Updating **secretgen-controller to v0.9.1**
  * SecretTemplate API: SecretTemplate resources introduce a highly flexible way of telling secretgen-controller to populate a single secret from fields in any other resource on the cluster selected via JSONpath.
  
* Updating Carvel CLIs
  * imgpkg to v0.29.0
  * kbld to v0.34.0 
  * ytt to v0.41.1 
  * kapp to v0.49.0


## <a id='1-1'></a> v1.1.0

**Release Date**: April 5, 2022

### <a id='1-1-new-features'></a> New features

* Updating **kapp-controller to v0.34.0**. This update brings in significant performance improvements when running large Package Repositories. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).

* Updating **secretgen-controller to v0.8.0**
