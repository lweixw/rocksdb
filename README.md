## Build rockdb for 5.18.4 in Apple Silicon machine

The rocksdb v5.18.4 is being used by Kafka stream(2.6.0+). When you are developing Kafka stream application, your unit tests with Kafka stream would fail due to there is no compatible binary provided for Apple Silicon.

The purpose of this branch is to build 5.18.14+ version in Apple Silicon machine. So that you could run & test application in your local machine.

**DO NOT USE IN PRODUCTION ENVIRONMENT**

### Prequesite

Java11 Azul Java 11 for Apple Silicon(aarch64)
Xcode or Xcode command line

### Command for build

DISABLE_WARNING_AS_ERROR=1 make shared_lib rocksdbjava

### artefacts

`$(ROCKSDB_ROOT)/java/target/rocksdbjni-5.18.4-osx.jar`
Copy & rename (to rocksdbjni-5.18.4.jar) the artefact above to your dependency cache folder (for maven or gradle, it's in ~/.m2/ or ~/.gradle/cache)

## RocksDB: A Persistent Key-Value Store for Flash and RAM Storage

[![Linux/Mac Build Status](https://travis-ci.org/facebook/rocksdb.svg?branch=master)](https://travis-ci.org/facebook/rocksdb)
[![Windows Build status](https://ci.appveyor.com/api/projects/status/fbgfu0so3afcno78/branch/master?svg=true)](https://ci.appveyor.com/project/Facebook/rocksdb/branch/master)
[![PPC64le Build Status](http://140.211.168.68:8080/buildStatus/icon?job=Rocksdb)](http://140.211.168.68:8080/job/Rocksdb)

RocksDB is developed and maintained by Facebook Database Engineering Team.
It is built on earlier work on LevelDB by Sanjay Ghemawat (sanjay@google.com)
and Jeff Dean (jeff@google.com)

This code is a library that forms the core building block for a fast
key value server, especially suited for storing data on flash drives.
It has a Log-Structured-Merge-Database (LSM) design with flexible tradeoffs
between Write-Amplification-Factor (WAF), Read-Amplification-Factor (RAF)
and Space-Amplification-Factor (SAF). It has multi-threaded compactions,
making it specially suitable for storing multiple terabytes of data in a
single database.

Start with example usage here: https://github.com/facebook/rocksdb/tree/master/examples

See the [github wiki](https://github.com/facebook/rocksdb/wiki) for more explanation.

The public interface is in `include/`.  Callers should not include or
rely on the details of any other header files in this package.  Those
internal APIs may be changed without warning.

Design discussions are conducted in https://www.facebook.com/groups/rocksdb.dev/

## License

RocksDB is dual-licensed under both the GPLv2 (found in the COPYING file in the root directory) and Apache 2.0 License (found in the LICENSE.Apache file in the root directory).  You may select, at your option, one of the above-listed licenses.
