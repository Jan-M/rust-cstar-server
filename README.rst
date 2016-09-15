Goal
====

Build a Rust implementation of the Cassandra Server API to be able to speak to the CQL native v5 protocol.

Reasoning
=========

Original need is to build an in memory time series store to handle lots of time series for 1-7 days with techniques following the Google Gorilla paper.

However this is of little need without any clients/UI tooling.

If we can speak CQL/Cassandra for the 3 queries required for KairosDB (lookup indexes, query time series, write data point) we can benefit from the existing tools/UI.

CQL protocol + Snappy/LZ4 should be sufficiently fast over HTTP+JSON and also allows e.g. transfer of binary blobs representing whole chunks of data.

Protocol
========

https://github.com/apache/cassandra/blob/trunk/doc/native_protocol_v5.spec

Existing implementations
========================

Seastar C++
https://github.com/scylladb/scylla/blob/master/transport/server.cc

Scala+Akka
https://github.com/scassandra/scassandra-server
