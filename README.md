# Apache Geode BOSH Release


## In development

Old CLI

```
bosh create release --name geode --force && bosh upload release && bosh -n -d manifest/manifest.yml deploy
```

New CLI

```
bosh create-release --name=geode --force && bosh -e vbox upload-release && bosh -e vbox -n -d geode deploy manifest/manifest.yml
```

## Create release tarball

Old CLI

```
bosh create release --name=geode --version=${VERSION} --final --with-tarball --force 
```

New CLI

```
VERSION=0.0.1
bosh create-release --name=geode --version=${VERSION} --final --tarball=geode-boshrelease-${VERSION}.tgz --force
```

## Deploy Geode Cluster

Configure [manifest/manifest.yml](manifest/manifest.yml) for your environment.

Old CLI

```
VERSION=0.0.1
bosh upload release https://github.com/making/geode-boshrelease/releases/download/${VERSION}/geode-boshrelease-${VERSION}.tgz
bosh -n -d manifest/manifest.yml deploy 
```

New CLI

```
VERSION=0.0.1
bosh -e vbox upload-release https://github.com/making/geode-boshrelease/releases/download/${VERSION}/geode-boshrelease-${VERSION}.tgz
bosh -e vbox -n -d geode deploy manifest/manifest.yml
```