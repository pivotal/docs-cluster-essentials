# Cluster Essentials Release notes

This topic contains release notes for Cluster Essentials for VMware Tanzu. A new minor release for Cluster Essentials is publish every quarter. Monthly patch releases are published to address critical bugs and CVEs, if there are any.

## <a id='1-4-8'></a> v1.4.8

**Release Date**: Dec 29, 2023

### <a id='1-4-8-resolved-issues'></a> Resolved issues
* Updating **kapp-controller to v0.44.12**. This patch release addresses CVEs identified in v1.4.7. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.44.12).
* Updating **secretgen-controller to v0.13.8**
* Updating Carvel CLIs
  * imgpkg to v0.33.9
  * kapp to v0.54.10
  * kbld to v0.36.12
  * ytt to v0.44.12

## <a id='1-4-7'></a> v1.4.7

**Release Date**: November 30, 2023

### <a id='1-4-7-resolved-issues'></a> Resolved issues
* Updating **kapp-controller to v0.44.11**. This patch release addresses CVEs identified in v1.4.6. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.44.11).
* Updating **secretgen-controller to v0.13.7**
* Updating Carvel CLIs
  * imgpkg to v0.33.8
  * kapp to v0.54.9
  * kbld to v0.36.11
  * ytt to v0.44.11

## <a id='1-4-6'></a> v1.4.6

**Release Date**: October 31, 2023

### <a id='1-4-6-resolved-issues'></a> Resolved issues
* Updating **kapp-controller to v0.44.10**. This patch release addresses CVEs identified in v1.4.5. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.44.10).
* Updating **secretgen-controller to v0.13.6**
* Updating Carvel CLIs
  * imgpkg to v0.33.7
  * kapp to v0.54.8
  * kbld to v0.36.10
  * ytt to v0.44.10

## <a id='1-4-5'></a> v1.4.5

**Release Date**: October 3, 2023

### <a id='1-4-5-resolved-issues'></a> Resolved issues
* Updating **kapp-controller to v0.44.9_vmware.2**. This patch release addresses CVEs identified in v1.4.4. 

## <a id='1-4-4'></a> v1.4.4

**Release Date**: August 31, 2023

### <a id='1-4-4-resolved-issues'></a> Resolved issues
* Updating **kapp-controller to v0.44.9**. This patch release addresses CVEs identified in v1.4.3. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.44.9).
* Updating **secretgen-controller to v0.13.5**
* Updating Carvel CLIs
  * imgpkg to v0.33.6
  * kapp to v0.54.7
  * kbld to v0.36.9
  * ytt to v0.44.9

## <a id='1-4-3'></a> v1.4.3

**Release Date**: July 31, 2023

### <a id='1-4-3-resolved-issues'></a> Resolved issues
* This patch release addresses CVEs identified in v1.4.2.

## <a id='1-4-2'></a> v1.4.2

**Release Date**: June 30, 2023

### <a id='1-4-2-resolved-issues'></a> Resolved issues
* Updating **kapp-controller to v0.44.8**. This patch release addresses CVEs identified in v1.4.1. A full list of fixes can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases/tag/v0.44.8).
* Updating **secretgen-controller to v0.13.3**
* Updating Carvel CLIs
  * imgpkg to v0.33.5
  * kapp to v0.54.5
  * kbld to v0.36.8
  * ytt to v0.44.8

## <a id='1-4-1'></a> v1.4.1

**Release Date**: February 14, 2023

### <a id='1-4-1-resolved-issues'></a> Resolved issues
* Support added automatic IaaS authentication for fetching images from IaaS provided registry, for example, ECR from EKS. 
* Adding support for OpenShift 4.10.
* Updating **kapp-controller to v0.44.6**. This patch release addresses CVE known issues identified in 1.4. A full list of new features can be found in the open source [release notes](https://github.com/vmware-tanzu/carvel-kapp-controller/releases).
* Updating **secretgen-controller to v0.13.0**
* Updating Carvel CLIs
  * imgpkg to v0.31.1
  * kapp to v0.54.3
  * kbld to v0.36.4
  * ytt to v0.44.3

## <a id='1-4'></a> v1.4.0

**Release Date**: January 9, 2023

### <a id='1-4-issues'></a> Known Issues
* Automatic IaaS authentication for fetching images from IaaS provided registry, for example, ECR from EKS, does not succeed. 
VMware recommends continued use of Cluster Essentials v1.3.0 if this feature is required.
* Due to a stricter seccomp profile, installation on OpenShift 4.10 will fail.
VMware recommends continued use of Cluster Essentials v1.3.0 if your environment is OpenShift 4.10.

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
