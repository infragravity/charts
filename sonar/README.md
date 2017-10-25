# Sonar-DS

[Sonar](https://github.com/infragravity/charts) is a server agent written .NET Core by developers at [Infragravity](https://infragravity.com) for collecting & reporting metrics. This chart runs a DaemonSet of Infragravity instances to collect SQL server and WMI metrics from pods on your cluster. If you need to poll individual instances of infrastructure or APIs there is a `stable/sonar` chart that may be more suitable to address this scenario.

## TL;DR

```console
$ helm install stable/sonar-ds
```

## Introduction

This chart bootstraps a `sonar-ds` deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

## Prerequisites

- Kubernetes 1.7+ with Beta APIs enabled

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ helm install --name my-release stable/sonar-ds
```

The command deploys Sonar daemonset on the Kubernetes cluster in the default configuration. The [configuration](#configuration) section as well as the [values.yaml](/values.yaml) file lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.
 
## Configuration

The default configuration parameters are listed in `values.yaml`. To change the defaults, specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,

```console
$ helm install --name my-release \
    stable/sonar-ds
```

The above command allows the chart to deploy Sonar with configuration of inputs to read metrics from and outputs to write to.

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart. For example,

```console
$ helm install --name my-release -f values.yaml stable/sonar-ds
```

## Sonar Configuration

This chart deploys the following by default:

- `sonar` (`sonar-ds`) running in a daemonset with the following plugins enabled
  * WSMAN - WMI metrics using WS-Management protocol
  * MSSQL - Sql Server