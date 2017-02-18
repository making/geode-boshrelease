
```
wget https://download.run.pivotal.io/openjdk-jdk/trusty/x86_64/openjdk-1.8.0_121.tar.gz
wget https://dist.apache.org/repos/dist/release/geode/1.1.0/apache-geode-1.1.0.tar.gz
```

### New CLI

```
bosh add-blob --dir=.. openjdk-1.8.0_121.tar.gz java/openjdk-1.8.0_121.tar.gz
bosh add-blob --dir=.. apache-geode-1.1.0.tar.gz geode/apache-geode-1.1.0.tar.gz
```

If you have an access for the S3 of cloudfoundry-community

```
bosh upload-blobs --dir=..
```

### Old CLI (might work)

```
bosh add blob openjdk-1.8.0_121.tar.gz java
bosh add blob apache-geode-1.1.0.tar.gz geode
```

If you have an access for the S3 of cloudfoundry-community

```
bosh upload blobs
```