---
title: Payshares Software
---
# Software

Pre-built software and services you can run on your own infrastructure, provided by Payshares.org.

## [Payshares Core](../payshares-core/learn/admin.html)
Payshares Core is the backbone of the Payshares network and does the hard work of validating and agreeing on the status of every transaction with other instances of Core through the Payshares Consensus Protocol (SCP).

## [Horizon](https://github.com/payshares/go/tree/master/services/horizon)
Horizon is the client-facing API server for the Payshares ecosystem. It acts as the interface between Payshares Core and applications that want to access the Payshares network. If you are running Payshares Core, you will probably also want to run Horizon.

## [Federation Server](https://github.com/payshares/go/tree/master/services/federation)
A standalone Federation protocol server designed to be dropped in to your existing infrastructure. It can be configured to pull the data it needs out of your existing SQL database.

| Platform       | Latest Release                                                                         |
|----------------|------------------------------------------------------------------------------------------|
| Mac OSX 64-bit (amd64) | [federation-darwin-amd64](https://github.com/payshares/go/releases/download/federation-v0.2.0/federation-v0.2.0-darwin-amd64.tar.gz)      |
| Linux 64-bit (amd64)  | [federation-linux-amd64](https://github.com/payshares/go/releases/download/federation-v0.2.0/federation-v0.2.0-linux-amd64.tar.gz)       |
| Linux 32-bit (arm)  | [federation-arm-amd64](https://github.com/payshares/go/releases/download/federation-v0.2.0/federation-v0.2.0-linux-arm.tar.gz)       |
| Windows 64-bit (amd64) | [federation-windows-amd64.exe](https://github.com/payshares/go/releases/download/federation-v0.2.0/federation-v0.2.0-windows-amd64.zip) |

## [Bridge Server](https://github.com/payshares/bridge-server)
Payshares’s Bridge server provides a simple interface for the Payshares network. It is meant to simplify compliance operations and other more complicated integrations. Because it stores and manages keys and account information, access to it should be well protected. Unlike Horizon, it should never be exposed to the public internet.

## [Archivist](https://github.com/payshares/go/tree/master/tools/payshares-archivist)
This is a small tool, written in Go, for working with payshares-core history archives directly. It is a standalone tool that does not require payshares-core, or any other programs.


| Platform       | Latest Release                                                                        |
|----------------|------------------------------------------------------------------------------------------|
| Mac OSX 64-bit (amd64) | [payshares-archivist-darwin-amd64](https://github.com/payshares/go/releases/download/payshares-archivist-v0.1.0/payshares-archivist-v0.1.0-darwin-amd64.tar.gz)      |
| Linux 64-bit (amd64)   | [payshares-archivist-linux-amd64](https://github.com/payshares/go/releases/download/payshares-archivist-v0.1.0/payshares-archivist-v0.1.0-linux-amd64.tar.gz)       |
| Linux 32-bit (arm)   | [payshares-archivist-linux-arm](https://github.com/payshares/go/releases/download/payshares-archivist-v0.1.0/payshares-archivist-v0.1.0-linux-arm.tar.gz)       |
| Windows 64-bit (amd64) | [payshares-archivist-windows-amd64.exe](https://github.com/payshares/go/releases/download/payshares-archivist-v0.1.0/payshares-archivist-v0.1.0-windows-amd64.zip) |
