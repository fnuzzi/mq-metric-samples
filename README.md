# mq-metric-samples

This repository contains a collection of IBM® MQ sample clients that utilize
the [IBM® MQ golang metric packages](https://github.com/ibm-messaging/mq-golang)
to provide a program that can be used with existing monitoring technologies
such as Prometheus, AWS CloudWatch, etc.

These samples were moved to this repository from
the [IBM® MQ golang metric packages repository](https://github.com/ibm-messaging/mq-golang).

## Health Warning

This package is provided as-is with no guarantees of support or updates.
There are also no guarantees of compatibility with any future versions of the package;
interfaces and functions are subject to change based on any feedback.

These samples use a specific version of the `mqmetric` and `ibmmq` golang packages.
Those packages are in the [mq-golang repository](https://github.com/ibm-messaging/mq-golang).

## Getting started

### Sample requirements

You will require the following programs:

* [dep](https://golang.github.io/dep/) - Golang dependency management tool

If using a version of Go from after 2017, you must set environment variables to permit some compile/link flags. This is due to a security fix in the compiler.

```
export CGO_LDFLAGS_ALLOW="-Wl,-rpath.*"
```

### Building a component

* Change directory to your go path. (`cd $GOPATH`)
* Use git to get a copy of this repository into a new directory in the workspace:

```
git clone https://github.com/ibm-messaging/mq-metric-samples.git src/github.com/ibm-messaging/mq-metric-samples
```

* Navigate to the mq-metric-samples root directory (`$GOPATH/src/github.com/ibm-messaging/mq-metric-samples`)
* Run dep to ensure that you have the correct dependencies downloaded:

```
dep ensure
```

* Compile the sample program you wish to use. For example to build the mq_prometheus sample:

```
go install cmd/mq_prometheus
```

At this point, you should have a compiled copy of the code in `$GOPATH/bin`. Each
monitor agent directory also has sample scripts, configuration files etc to help
with getting the agent running in your specific environment.

## More information
Each of the sample monitor programs has its own README file describing the
capabilities in more detail. In general, the Prometheus monitor program is
likely to be the most recent, supporting the newest features of the MQ APIs.

## History

See [CHANGELOG](CHANGELOG.md) in this directory.

## Issues and Contributions

For feedback and issues relating specifically to this package, please use the [GitHub issue tracker](https://github.com/ibm-messaging/mq-golang/issues).

Contributions to this package can be accepted under the terms of the IBM Contributor License
Agreement, found in the [CLA file](CLA.md) of this repository. When submitting a pull request, you
must include a statement stating you accept the terms in the CLA.

## Copyright

© Copyright IBM Corporation 2016, 2018
