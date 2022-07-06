# Deploying Cluster Essentials v1.2

This document describes how to install, upgrade, and uninstall Cluster Essentials v1.2.

## <a id='supported-platforms'></a> Supported Platforms

Currently, Cluster Essentials only supports MacOS and Linux. 

## <a id='supported-kube'></a> Supported Kubernetes versions

Installation requires Kubernetes cluster v1.2.0, v1.21, v1.22, v1.23, or v1.24 on one of the following Kubernetes
providers:

- Azure Kubernetes Service
- Amazon Elastic Kubernetes Service
- Google Kubernetes Engine
    - GKE Autopilot clusters do not have required features enabled
- Minikube
- Kind

## <a id='install'></a> Install

If you are using a VMware Tanzu Kubernetes Grid cluster, you do not need to install Cluster Essentials because the contents of Cluster Essentials are already installed on your cluster.

For all other clusters, install Cluster Essentials using the following steps.

### <a id='download'></a> Download artifacts from Tanzu Network

1. Sign in to [Tanzu Network](https://network.tanzu.vmware.com).

1. Go to [Cluster Essentials for VMware Tanzu](https://network.tanzu.vmware.com/products/tanzu-cluster-essentials/) on VMware Tanzu Network.

1. Accept or confirm that you have accepted the EULA for the product

1.  Select a download according to your Kubernetes provider and operating system:

    - For macOS, download `tanzu-cluster-essentials-darwin-amd64-1.2.0.tgz`.
    - For Linux, download `tanzu-cluster-essentials-linux-amd64-1.2.0.tgz`.

1. Unpack the TAR file into the `tanzu-cluster-essentials` directory:

    ```
    mkdir $HOME/tanzu-cluster-essentials
    tar -xvf DOWNLOADED-CLUSTER-ESSENTIALS-BUNDLE -C $HOME/tanzu-cluster-essentials
    ```

    Where `DOWNLOADED-CLUSTER-ESSENTIALS-BUNDLE` is the name of the bundle you downloaded.

### <a id='cluster-context'></a> Set Kubernetes cluster context

1. List the existing contexts by running:

    ```
    kubectl config get-contexts
    ```


1.  Set the context to the cluster that you want to use for the Cluster Essentials install.

    ```
    kubectl config use-context CONTEXT-NAME
    ```

### <a id='install'></a> Deploy onto cluster

1. (Optional) If your registry needs a custom certificate, you must [load that configuration](https://carvel.dev/kapp-controller/docs/v0.38.0/controller-config/) into the cluster before installing `kapp-controller`. If your registry uses a public certificate, this step is not required.

   Create the `kapp-controller` namespace:

    ```
    kubectl create namespace kapp-controller
    ```

   Create a configuration secret by using the registry's `ca.crt` stored on local disk:

    ```
    kubectl create secret generic kapp-controller-config \
       --namespace kapp-controller \
       --from-file caCerts=ca.crt
    ```

1. Configure and run `install.sh`, which will install `kapp-controller` and `secretgen-controller` on your cluster:

    - For online installation, run:

        ```
        export INSTALL_BUNDLE=registry.tanzu.vmware.com/tanzu-cluster-essentials/cluster-essentials-bundle@sha256:c7c4cb124c06ca0b6a5a6c31617781fd5b4513e03df1cb49d5d19e91c7166644
        export INSTALL_REGISTRY_HOSTNAME=registry.tanzu.vmware.com
        export INSTALL_REGISTRY_USERNAME=TANZU-NET-USER
        export INSTALL_REGISTRY_PASSWORD=TANZU-NET-PASSWORD
        cd $HOME/tanzu-cluster-essentials
        ./install.sh --yes
        ```
        
        Where `TANZU-NET-USER` and `TANZU-NET-PASSWORD` are your credentials for VMware Tanzu Network.

    - For air-gapped installation, run:

        ```
        $ IMGPKG_REGISTRY_HOSTNAME=registry.tanzu.vmware.com \
          IMGPKG_REGISTRY_USERNAME=TANZUNET-REGISTRY-USERNAME \
          IMGPKG_REGISTRY_PASSWORD=TANZUNET-REGISTRY-PASSWORD \
          imgpkg copy \
            -b registry.tanzu.vmware.com/tanzu-cluster-essentials/cluster-essentials-bundle@sha256:c7c4cb124c06ca0b6a5a6c31617781fd5b4513e03df1cb49d5d19e91c7166644 \
            --to-tar cluster-essentials-bundle-1.2.0.tar \
            --include-non-distributable-layers

        $ IMGPKG_REGISTRY_HOSTNAME=MY-REGISTRY \
          IMGPKG_REGISTRY_USERNAME=MY-REGISTRY-USER \
          IMGPKG_REGISTRY_PASSWORD=MY-REGISTRY-PASSWORD \
          imgpkg copy \
            --tar cluster-essentials-bundle-1.2.0.tar \
            --to-repo CUSTOMER-REGISTRY-HOSTNAME/cluster-essentials-bundle \
            --include-non-distributable-layers \
            --registry-ca-cert-path CA_PATH
        $ INSTALL_BUNDLE=CUSTOMER-REGISTRY-HOSTNAME/cluster-essentials-bundle:1.2.0 \
          INSTALL_REGISTRY_HOSTNAME=MY-REGISTRY \
          INSTALL_REGISTRY_USERNAME=MY-REGISTRY-USER \
          INSTALL_REGISTRY_PASSWORD=MY-REGISTRY-PASSWORD \
          ./install.sh
        ```

        Where:

        - `TANZUNET-REGISTRY-USERNAME` is your username of the VMware Tanzu Network.
        - `TANZUNET-REGISTRY-PASSWORD` is your password of the VMware Tanzu Network.
        - `MY-REGISTRY` is your air-gapped container registry.
        - `MY-REGISTRY-USER` is the user with write access to `MY-REGISTRY`.
        - `MY-REGISTRY-PASSWORD` is the password for `MY-REGISTRY-USER`.

### <a id='cli-install'></a> Optionally install CLIs onto your `$PATH`
1. (Optional) Several Tanzu products, such as Tanzu Application Platform, use the `kapp` CLI to deploy. For convenience, you may install the `kapp` CLI onto your `$PATH`:

    ```
    sudo cp $HOME/tanzu-cluster-essentials/kapp /usr/local/bin/kapp
    ```

1. (Optional) Several Tanzu products, such as Tanzu Application Platform, use the `imgpkg` CLI to relocate packages. For convenience, you may install the `imgpkg` CLI onto your `$PATH`:

    ```
    sudo cp $HOME/tanzu-cluster-essentials/imgpkg /usr/local/bin/imgpkg
    ```

## <a id='upgrade'></a> Upgrade
Cluster Essentials components (such as `kapp-controller` and `secretgen-controller`) cannot be upgraded on clusters provisioned using VMware Tanzu Kubernetes Grid, Tanzu Community Edition, and VMware Tanzu Mission Control. 

For all other clusters, if you already have Cluster Essentials 1.0 installed on your target cluster, you can upgrade to Cluster Essentials 1.2 using the following steps. Running this upgrade will update the `kapp-controller` version on your cluster to `v0.38.3` and `secretgen-controller` version to `v0.9.1`.

1. Follow the steps above to [Download artifacts from Tanzu Network](#download) and [Set Kubernetes cluster context](#cluster-context)

1. Configure and run `install.sh`, which will install `kapp-controller` and `secretgen-controller` on your cluster:

    ```
    export INSTALL_BUNDLE=registry.tanzu.vmware.com/tanzu-cluster-essentials/cluster-essentials-bundle@sha256:c7c4cb124c06ca0b6a5a6c31617781fd5b4513e03df1cb49d5d19e91c7166644
    export INSTALL_REGISTRY_HOSTNAME=registry.tanzu.vmware.com
    export INSTALL_REGISTRY_USERNAME=TANZU-NET-USER
    export INSTALL_REGISTRY_PASSWORD=TANZU-NET-PASSWORD
    cd $HOME/tanzu-cluster-essentials
    ./install.sh --yes
    ```

    Where `TANZU-NET-USER` and `TANZU-NET-PASSWORD` are your credentials for VMware Tanzu Network.

1. Follow the [steps above](#cli-install) to optionally install newer versions of the `kapp` and `imgpkg` CLIs to your path 


## <a id='uninstall'></a> Uninstall
**Caution:** Please ensure that you have uninstalled all Custom Resources created by `kapp-controller` and `secretgen-controller` before running the uninstall script for Cluster Essentials.

1. Follow the steps above to [Set Kubernetes cluster context](#cluster-context)

1. Run `uninstall.sh`, which will uninstall `kapp-controller` and `secretgen-controller` on your cluster:

    ```
    cd $HOME/tanzu-cluster-essentials
    ./uninstall.sh --yes
    ```
