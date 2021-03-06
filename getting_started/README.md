# Getting started

Here is a guide on how to install *dncli* command line interface and connect to dfinance testnet.

## Installation using precompiled binaries

First of all download the latest version of **dncli** for your system from [release pages](https://github.com/dfinance/dnode/releases).

Install downloaded **dncli** binary.

For Mac OS/Linux:

    mv <downloaded binary path> ./dncli
    chmod +x ./dncli
    mv ./dncli /usr/local/bin/dncli

For Windows:

TODO

Check that installation successful done by running the command:

    dncli version

Your should see your current version of **dncli** in output.

Let's configure **dncli** and after go to the next step:

    dncli config chain-id dn-testnet
    dncli config output json
    dncli config indent true
    dncli config trust-node true
    dncli config compiler rpc.testnet.dfinance.co:50053
    dncli config node rpc.testnet.dfinance.co:26657

These configurations will connect your local **dncli** with remote testnet nodes.

Check that **dncli** configurated correctly:

    dncli status

## Installation from sources

Before we start you should have a correct 'GOPATH', 'GOROOT' environment variables.

Required:

    * golang 1.13.8 or later.
    * protoc - here is [installation instruction](https://www.grpc.io/docs/quickstart/go/).

### Build and Install using Makefile


Clone dfinance node repository to suitable place

    git clone https://github.com/dfinance/dnode.git

Build and install *dncli* as binary using Makefile

    make install-dncli

So after this command *dncli* will be available from console

    dncli version --long


### Build without Makefile

And let's build *dncli*:

    GO111MODULE=on go build -o dncli cmd/dncli/main.go

Command must execute fine, after it you can run *dncli*:

    GO111MODULE=on go run cmd/dncli/main.go
