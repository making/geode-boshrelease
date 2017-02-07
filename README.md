# Apache Geode BOSH Release


## In development

```
bosh create-release --name=geode --force && bosh -e vbox upload-release && bosh -e vbox -n -d geode deploy manifest/manifest.yml
```

## Create release tarball

```
VERSION=0.0.1
bosh create-release --name=geode --version=${VERSION} --final --tarball=geode-boshrelease-${VERSION}.tgz --force
```

## Deploy Geode Cluster

Configure [manifest/manifest.yml](manifest/manifest.yml) for your environment.

```
bosh -e vbox upload-release https://github.com/making/geode-boshrelease/releases/download/0.0.1/geode-boshrelease-0.0.1.tgz
bosh -e vbox -n -d geode deploy manifest/manifest.yml
```