
```
wget https://download.run.pivotal.io/openjdk-jdk/trusty/x86_64/openjdk-1.8.0_121.tar.gz
wget https://archive.apache.org/dist/incubator/geode/1.0.0-incubating/apache-geode-1.0.0-incubating.tar.gz
```

### New CLI

```
bosh add-blob --dir=.. openjdk-1.8.0_121.tar.gz java 
bosh add-blob --dir=.. apache-geode-1.0.0-incubating.tar.gz geode 
```

If you have an access for the S3 of cloudfoundry-community

```
bosh upload-blobs
```

### Old CLI (might work)

```
bosh add blob openjdk-1.8.0_121.tar.gz java
bosh add blob apache-geode-1.0.0-incubating.tar.gz geode
```

If you have an access for the S3 of cloudfoundry-community

```
bosh upload blobs
```