
```
wget https://download.run.pivotal.io/openjdk-jdk/trusty/x86_64/openjdk-1.8.0_121.tar.gz
wget http://ftp.jaist.ac.jp/pub/apache/geode/1.0.0-incubating/apache-geode-1.0.0-incubating.tar.gz
```

### Old CLI

```
bosh add blob openjdk-1.8.0_121.tar.gz java
bosh add blob apache-geode-1.0.0-incubating.tar.gz geode
```

### New CLI

```
bosh -e vbox add-blob --dir=.. openjdk-1.8.0_121.tar.gz java 
bosh -e vbox add-blob --dir=.. apache-geode-1.0.0-incubating.tar.gz geode 
```
