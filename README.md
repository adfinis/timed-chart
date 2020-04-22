# Timed Application

## Introduction
This chart runs a [timed](https://github.com/adfinis-sygroup/timed-frontend) deployment on a [Kubernetes](https://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

Chart releases can be listed on the [releases](https://github.com/adfinis-sygroup/timed-chart/releases) page.

Source code can be found here:
* timed-frontend: https://github.com/adfinis-sygroup/timed-frontend
* timed-backend: https://github.com/adfinis-sygroup/timed-backend

## Prerequisites

* Kubernetes 1.17+
* PV provisioner support in the underlying infrastructure
* Helm 3

## Installing the Chart
To install the chart with the release name `my-release` run the following command:

```bash
$ helm repo add timed https://adfinis-sygroup.github.io/timed-chart
$ helm install my-release timed/timed--set ingress.hosts={"test-timed.example.com"}
```
The command deploys Timed on a Kubernetes cluster and sets an ingress hostname for external access.

For simple testing without any persistence you can run the following:

```bash
$ helm install my-release timed/timed --set ingress.hosts={"test-timed.example.com"} --set postgresql.persistence.enabled=false
`
```

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```bash
$ helm delete my-release
```

## Chart Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | postgresql | ~8.7.3 |

## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| backend.image.pullPolicy | string | `"IfNotPresent"` | Backend image pull policy |
| backend.image.repository | string | `"adfinissygroup/timed-backend"` | Backend image name |
| backend.livenessProbe.enabled | bool | `true` | Enable liveness probe for backend |
| backend.livenessProbe.failureThreshold | int | `6` | Number of times the backend liveness probe is allowed to fail |
| backend.livenessProbe.initialDelaySeconds | int | `60` | Number of seconds the backend liveness probe waits before execution |
| backend.livenessProbe.periodSeconds | int | `10` | How often (in seconds) to perform the backend liveness probe |
| backend.livenessProbe.successThreshold | int | `1` | Minimum consecutive successes for the backend liveness probe to be considered successful after having failed |
| backend.livenessProbe.timeoutSeconds | int | `5` | Number of seconds after which the backend liveness probe times out |
| backend.readinessProbe.enabled | bool | `true` | Enable readiness probe for backend |
| backend.readinessProbe.failureThreshold | int | `6` | Number of times the backend readiness probe is allowed to fail |
| backend.readinessProbe.initialDelaySeconds | int | `30` | Number of seconds the backend readiness probe waits before execution |
| backend.readinessProbe.periodSeconds | int | `10` | How often (in seconds) to perform the backend readiness probe |
| backend.readinessProbe.successThreshold | int | `1` | Minimum consecutive successes for the backend readiness probe to be considered successful after having failed |
| backend.readinessProbe.timeoutSeconds | int | `5` | Number of seconds after which the backend readiness probe times out |
| backend.replicaCount | int | `1` | Number of backend instances |
| backend.resources | object | `{}` | Resource limits for backend |
| backend.service.externalPort | int | `80` | Backend external Port |
| backend.service.internalPort | int | `80` | Backend internal Port |
| backend.service.name | string | `"timed-backend"` | Name of the backend service |
| backend.service.type | string | `"ClusterIP"` | Backend service type |
| backend.settings.emailFrom | string | `"webmaster@chart-example.local"` | Default email address to use for various responses for Django |
| backend.settings.emailUrl | string | `"smtp://localhost:25"` | Connection string for email server for Django |
| backend.settings.serverEmail | string | `"webmaster@chart-example.local"` | Email address error messages are sent from for Django |
| frontend.image.pullPolicy | string | `"IfNotPresent"` | Frontend image pull policy |
| frontend.image.repository | string | `"adfinissygroup/timed-frontend"` | Frontend image name |
| frontend.livenessProbe.enabled | bool | `true` | Enable liveness probe for frontend |
| frontend.livenessProbe.failureThreshold | int | `6` | Number of times the frontend liveness probe is allowed to fail |
| frontend.livenessProbe.initialDelaySeconds | int | `60` | Number of seconds the frontend liveness probe waits before execution |
| frontend.livenessProbe.periodSeconds | int | `10` | How often (in seconds) to perform the frontend liveness probe |
| frontend.livenessProbe.successThreshold | int | `1` | Minimum consecutive successes for the frontend liveness probe to be considered successful after having failed |
| frontend.livenessProbe.timeoutSeconds | int | `5` | Number of seconds after which the frontend liveness probe times out |
| frontend.readinessProbe.enabled | bool | `true` | Enable readiness probe for frontend |
| frontend.readinessProbe.failureThreshold | int | `6` | Number of times the frontend readiness probe is allowed to fail |
| frontend.readinessProbe.initialDelaySeconds | int | `30` | Number of seconds the frontend readiness probe waits before execution |
| frontend.readinessProbe.periodSeconds | int | `10` | How often (in seconds) to perform the frontend readiness probe |
| frontend.readinessProbe.successThreshold | int | `1` | Minimum consecutive successes for the frontend readiness probe to be considered successful after having failed |
| frontend.readinessProbe.timeoutSeconds | int | `5` | Number of seconds after which the frontend readiness probe times out |
| frontend.replicaCount | int | `1` | Number of frontend instances |
| frontend.resources | object | `{}` | Resource limits for frontend |
| frontend.service.externalPort | int | `80` | Frontend external Port |
| frontend.service.internalPort | int | `80` | Frontend internal Port |
| frontend.service.name | string | `"timed-frontend"` | Name of the frontend service |
| frontend.service.type | string | `"ClusterIP"` | Frontend service type |
| ingress.annotations | object | `{}` | Ingress annotations |
| ingress.enabled | bool | `false` | Enable ingress |
| ingress.hosts | list | `[]` | Ingress hostnames |
| ingress.tls | list | `[]` | Ingress TLS parameter |
| postgresql.enabled | bool | `true` | Enable [Bitnami Postgresql chart](https://github.com/bitnami/charts/tree/master/bitnami/postgresql/) |
| postgresql.image.tag | string | `"12.2.0"` | Image tag of Postgres |
| postgresql.postgresqlDatabase | string | `"timed"` | Postgres Database name |
| postgresql.postgresqlUsername | string | `"postgres"` | Postgres Database username |
