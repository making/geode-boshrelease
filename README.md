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