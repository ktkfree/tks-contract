# tks-contract

[![Go Report Card](https://goreportcard.com/badge/github.com/sktelecom/tks-contract?style=flat-square)](https://goreportcard.com/report/github.com/sktelecom/tks-contract)
[![Go Reference](https://pkg.go.dev/badge/github.com/sktelecom/tks-contract.svg)](https://pkg.go.dev/github.com/sktelecom/tks-contract)
[![Release](https://img.shields.io/github/release/sktelecom/tks-contract.svg?style=flat-square)](https://github.com/sktelecom/tks-contract/releases/latest)

Tks-contract is one of the tks services. It mainly deals with the contract information.  
This service communicates based on gRPC. You can refer to the proto files in [tks-proto](https://github.com/sktelecom/tks-proto).

## Quick Start

### For go developers

```
go install -v ./...
contract-server -port 50051 -enable-mockup
```
### For docker users
```
TAGS=$(curl --silent "https://api.github.com/repos/sktelecom/tks-contract/tags" | grep name | head -1 |cut -d '"' -f 4)
docker pull docker.pkg.github.com/sktelecom/tks-contract/tks-contract:$TAGS
docker run --name tks-contract -p 50051:50051 -d \
  docker.pkg.github.com/sktelecom/tks-contract/tks-contract:$TAGS \
  contract-server \
  # -enable-mockup \
  # -port 50051
```

