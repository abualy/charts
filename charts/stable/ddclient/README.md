# ddclient

![Version: 3.2.1](https://img.shields.io/badge/Version-3.2.1-informational?style=flat-square) ![AppVersion: 3.9.1](https://img.shields.io/badge/AppVersion-3.9.1-informational?style=flat-square)

Perl client used to update dynamic DNS entries for accounts on Dynamic DNS Network Service Providers

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/ddclient/ddclient>
* <https://hub.docker.com/r/linuxserver/ddclient>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 1.0.0 |

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install ddclient k8s-at-home/ddclient
```

## Installing the Chart

To install the chart with the release name `ddclient`

```console
helm install ddclient k8s-at-home/ddclient
```

## Uninstalling the Chart

To uninstall the `ddclient` deployment

```console
helm uninstall ddclient
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install ddclient \
  --set env.TZ="America/New York" \
    k8s-at-home/ddclient
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install ddclient k8s-at-home/ddclient -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| config | string | `"# This is the configuration for ddclient\n# Inorder for it to function you need to set it up\n# e.g. this is the config for Cloudflare\ndaemon=600\nuse=web\nweb=dynamicdns.park-your-domain.com/getip\nprotocol=cloudflare\nssl=yes\nttl=1\nlogin=${CF_EMAIL}\npassword=${CF_GLOBAL_APIKEY}\nzone=${DOMAIN}.${TLD}\n${DOMAIN}.${TLD}\n"` |  |
| env | object | `{}` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"linuxserver/ddclient"` |  |
| image.tag | string | `"version-v3.9.1"` |  |
| ingress.enabled | bool | `false` |  |
| probes.liveness.enabled | bool | `false` |  |
| probes.readiness.enabled | bool | `false` |  |
| probes.startup.enabled | bool | `false` |  |
| service.enabled | bool | `false` |  |
| strategy.type | string | `"Recreate"` |  |

## Changelog

All notable changes to this application Helm chart will be documented in this file but does not include changes from our common library. To read those click [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common#changelog).

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

### [1.0.0]

#### Added

- N/A

#### Changed

- N/A

#### Removed

- N/A

[1.0.0]: #1.0.0

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)