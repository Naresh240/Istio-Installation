# Istio-Installation

# DOWNLOAD AND INSTALL ISTIOCLI

```bash
echo 'export ISTIO_VERSION="1.14.1"' >> ${HOME}/.bash_profile
source ${HOME}/.bash_profile

## Download Istio Version file
mkdir environment
cd ~/environment
curl -L https://istio.io/downloadIstio | ISTIO_VERSION=${ISTIO_VERSION} sh -

## Copy binary to $PATH
cd ${HOME}/environment/istio-${ISTIO_VERSION}
sudo cp -v bin/istioctl /usr/bin/

## Istio Version
istioctl version --remote=false
```

# INSTALL ISTIO

```bash
yes | istioctl install --set profile=demo

## Check the corresponding pods
kubectl get pods -n istio-system
```
