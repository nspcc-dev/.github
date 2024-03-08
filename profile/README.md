Neo SPCC is an R&D team developing an open-source truly decentralized cloud
platform and supporting the Neo core. Our main products are NeoFS and NeoGo.

We operate as an open community, PR and issues are welcome in every repository,
but to get some understanding of how we work and what we expect from
contributors take a look at our [.github](https://github.com/nspcc-dev/.github)
repository. Below is an outline of major repositories maintained by us.

# NeoFS

NeoFS is a decentralized distributed object storage system integrated with the
Neo blockchain. There are two public NeoFS networks, mainnet and testnet
associated with the respective Neo networks. But if you're looking at our
Github, then you should know there are ways to run your own private network
as well.

## Documentation

Take a look at [the specification](https://github.com/nspcc-dev/neofs-spec), it
explains most of the concepts and provides both a high-level overview and a
detailed API explanation.

[neofs-sdk-go](https://github.com/nspcc-dev/neofs-sdk-go/) ([godoc](https://pkg.go.dev/github.com/nspcc-dev/neofs-sdk-go))
is the way to programmatically interact with the system. If you need a
definition of the core NeoFS API, that'd be [neofs-api](https://github.com/nspcc-dev/neofs-api).

## Private networks

The easiest way to get a NeoFS instance with complete API support for initial
testing or application development is [neofs-aio](https://github.com/nspcc-dev/neofs-aio).

More complex scenarios with multiple nodes can be tested with [neofs-dev-env](https://github.com/nspcc-dev/neofs-dev-env/),
but it's more intended for people developing NeoFS itself.

## Nodes and CLI

NeoFS node source code and releases with all of the appropriate binaries can be
found in the [neofs-node](https://github.com/nspcc-dev/neofs-node) repository.
They can also be used to run a storage node of your own on public networks
(mainnet/testnet).

Maintaining a node instance can be easier with [ansible-neofs](https://github.com/nspcc-dev/ansible-neofs)
Ansible collection.

### Tests

NeoFS test suite (including gateway tests) can be found in [neofs-testcases](https://github.com/nspcc-dev/neofs-testcases).

NeoFS k6 extension for performance testing is in [xk6-neofs](https://github.com/nspcc-dev/xk6-neofs).

## Gateways

NeoFS nodes provide only NeoFS API, but there are additional services
implementing layers above this API, they're called gateways:
 * [neofs-http-gw](https://github.com/nspcc-dev/neofs-http-gw) implements basic operations with a simple HTTP, can be managed with [ansible-neofs](https://github.com/nspcc-dev/ansible-neofs)
 * [neofs-rest-gw](https://github.com/nspcc-dev/neofs-rest-gw) makes NeoFS API a RESTful one, can be managed with [ansible-neofs](https://github.com/nspcc-dev/ansible-neofs)
 * [neofs-s3-gw](https://github.com/nspcc-dev/neofs-s3-gw) implements a compatible subset of Amazon S3 protocol, can be managed with [ansible-neofs](https://github.com/nspcc-dev/ansible-neofs)

## Applications

[send-fs-neo-org](https://github.com/nspcc-dev/send-fs-neo-org) is a simple
example of application built on top of NeoFS. It uses [neofs-oauthz](https://github.com/nspcc-dev/neofs-oauthz)
internally to authenticate users (and issue bearer tokens for them).

[panel-fs-neo-org](https://github.com/nspcc-dev/panel-fs-neo-org) is an example
of NeoFS data management application.

Popular application forks with NeoFS support added:
 * [distribution](https://github.com/nspcc-dev/distribution)
 * [rclone](https://github.com/nspcc-dev/rclone)
 * [restic](https://github.com/nspcc-dev/restic)

# NeoGo

Take a look at [neo-go](https://github.com/nspcc-dev/neo-go) repository, it's
all there. [ansible-neogo-n3](https://github.com/nspcc-dev/ansible-neogo-n3)
can help you running it.

To learn more about Neo smart contract development in go take a look at [neo-go-sc-wrkshp](https://github.com/nspcc-dev/neo-go-sc-wrkshp).

There is also a Neo performance testing tool, [neo-bench](https://github.com/nspcc-dev/neo-bench).
