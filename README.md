# Apache Geode BOSH Release

Note that this release is developed with [BOSH CLI v2](http://bosh.io/docs/cli-v2.html).



## New CLI

### In development


```
export BOSH_CLIENT=admin
export BOSH_CLIENT_SECRET=`bosh int ~/deployments/vbox/creds.yml --path /admin_password`
export BOSH_CA_CERT=`bosh int ~/deployments/vbox/creds.yml --path /director_ssl/ca`
export BOSH_ENVIRONMENT=192.168.50.6
```

```
bosh create-release --name=geode --force && bosh -e vbox upload-release && bosh -e vbox -n -d geode deploy manifest/manifest.yml
```

### Create release tarball

```
VERSION=0.0.1
bosh create-release --name=geode --version=${VERSION} --final --tarball=geode-boshrelease-${VERSION}.tgz --force
```

### Deploy Geode Cluster

Configure [manifest/manifest.yml](manifest/manifest.yml) for your environment.

```
VERSION=0.0.1
bosh upload-release https://github.com/making/geode-boshrelease/releases/download/${VERSION}/geode-boshrelease-${VERSION}.tgz
bosh -n -d geode deploy manifest/manifest.yml
```

## Old CLI (might work)

### In development

```
bosh create release --name geode --force && bosh upload release && bosh -n -d manifest/manifest.yml deploy
```

### Create release tarball

```
bosh create release --name=geode --version=${VERSION} --final --with-tarball --force 
```

### Deploy Geode Cluster

Configure [manifest/manifest.yml](manifest/manifest.yml) for your environment.

```
VERSION=0.0.1
bosh upload release https://github.com/making/geode-boshrelease/releases/download/${VERSION}/geode-boshrelease-${VERSION}.tgz
bosh -n -d manifest/manifest.yml deploy 
```


