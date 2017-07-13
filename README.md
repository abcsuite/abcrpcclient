abcrpcclient
============

[![Build Status](http://img.shields.io/travis/abcsuite/abcrpcclient.svg)](https://travis-ci.org/abcsuite/abcrpcclient)
[![ISC License](http://img.shields.io/badge/license-ISC-blue.svg)](http://copyfree.org)
[![GoDoc](https://img.shields.io/badge/godoc-reference-blue.svg)](http://godoc.org/github.com/abcsuite/abcrpcclient)

abcrpcclient implements a Websocket-enabled Aero JSON-RPC client package
written in [Go](http://golang.org/).  It provides a robust and easy to use
client for interfacing with a Aero RPC server that uses a
abcd/bitcoin core-like compatible Aero JSON-RPC API.

## Status

This package is currently under active development.  It is already stable and
the infrastructure is complete.  However, there are still several RPCs left to
implement and the API is not stable yet.

## Documentation

* [API Reference](http://godoc.org/github.com/abcsuite/abcrpcclient)
* [abcd Websockets Example](https://github.com/abcsuite/abcrpcclient/blob/master/examples/dcrdwebsockets)  
  Connects to a abcd RPC server using TLS-secured websockets, registers for
  block connected and block disconnected notifications, and gets the current
  block count
* [dcrwallet Websockets Example](https://github.com/abcsuite/abcrpcclient/blob/master/examples/dcrwalletwebsockets)  
  Connects to a dcrwallet RPC server using TLS-secured websockets, registers for
  notifications about changes to account balances, and gets a list of unspent
  transaction outputs (utxos) the wallet can sign

## Major Features

* Supports Websockets (abcd/dcrwallet) and HTTP POST mode (bitcoin core-like)
* Provides callback and registration functions for abcd/dcrwallet notifications
* Supports abcd extensions
* Translates to and from higher-level and easier to use Go types
* Offers a synchronous (blocking) and asynchronous API
* When running in Websockets mode (the default):
  * Automatic reconnect handling (can be disabled)
  * Outstanding commands are automatically reissued
  * Registered notifications are automatically reregistered
  * Back-off support on reconnect attempts

## Installation

```bash
$ go get github.com/abcsuite/abcrpcclient
```

## Docker

All tests and linters may be run in a docker container using the script `run_tests.sh`.  This script defaults to using the current supported version of go.  You can run it with the major version of go you would like to use as the only arguement to test a previous on a previous version of go (generally Aero supports the current version of go and the previous one).

```
./run_tests.sh 1.7
```

To run the tests locally without docker:

```
./run_tests.sh local
```

## License

Package abcrpcclient is licensed under the [copyfree](http://copyfree.org) ISC
License.
