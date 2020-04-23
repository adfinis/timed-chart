timed
=====
Chart for Timed application

Current chart version is `0.3.3`

Source code can be found [here](https://github.com/adfinis-sygroup/timed-frontend)

## Chart Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | postgresql | ~8.7.3 |

## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| backend.image.pullPolicy | string | `"IfNotPresent"` | Backend image pull policy |
| backend.image.repository | string | `"adfinissygroup/timed-backend"` | Backend image name |
| backend.livenessProbe.enabled | bool | `true` |  |
| backend.livenessProbe.failureThreshold | int | `6` |  |
| backend.livenessProbe.initialDelaySeconds | int | `60` |  |
| backend.livenessProbe.periodSeconds | int | `10` |  |
| backend.livenessProbe.successThreshold | int | `1` |  |
| backend.livenessProbe.timeoutSeconds | int | `5` |  |
| backend.readinessProbe.enabled | bool | `true` |  |
| backend.readinessProbe.failureThreshold | int | `6` |  |
| backend.readinessProbe.initialDelaySeconds | int | `30` |  |
| backend.readinessProbe.periodSeconds | int | `10` |  |
| backend.readinessProbe.successThreshold | int | `1` |  |
| backend.readinessProbe.timeoutSeconds | int | `5` |  |
| backend.replicaCount | int | `1` | Number of Backend replicas |
| backend.resources | object | `{}` |  |
| backend.service.externalPort | int | `80` |  |
| backend.service.internalPort | int | `80` |  |
| backend.service.name | string | `"timed-backend"` | Backend service name |
| backend.service.type | string | `"ClusterIP"` |  |
| backend.settings.emailFrom | string | `"webmaster@chart-example.local"` |  |
| backend.settings.emailUrl | string | `"smtp://localhost:25"` |  |
| backend.settings.serverEmail | string | `"webmaster@chart-example.local"` |  |
| frontend.image.pullPolicy | string | `"IfNotPresent"` |  |
| frontend.image.repository | string | `"adfinissygroup/timed-frontend"` |  |
| frontend.livenessProbe.enabled | bool | `true` |  |
| frontend.livenessProbe.failureThreshold | int | `6` |  |
| frontend.livenessProbe.initialDelaySeconds | int | `60` |  |
| frontend.livenessProbe.periodSeconds | int | `10` |  |
| frontend.livenessProbe.successThreshold | int | `1` |  |
| frontend.livenessProbe.timeoutSeconds | int | `5` |  |
| frontend.readinessProbe.enabled | bool | `true` |  |
| frontend.readinessProbe.failureThreshold | int | `6` |  |
| frontend.readinessProbe.initialDelaySeconds | int | `30` |  |
| frontend.readinessProbe.periodSeconds | int | `10` |  |
| frontend.readinessProbe.successThreshold | int | `1` |  |
| frontend.readinessProbe.timeoutSeconds | int | `5` |  |
| frontend.replicaCount | int | `1` |  |
| frontend.resources | object | `{}` |  |
| frontend.service.externalPort | int | `80` |  |
| frontend.service.internalPort | int | `80` |  |
| frontend.service.name | string | `"timed-frontend"` |  |
| frontend.service.type | string | `"ClusterIP"` |  |
| ingress.annotations | object | `{}` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts | list | `[]` |  |
| ingress.tls | list | `[]` |  |
| postgresql.enabled | bool | `true` |  |
| postgresql.image.tag | string | `"12.2.0"` |  |
| postgresql.postgresqlDatabase | string | `"timed"` |  |
| postgresql.postgresqlUsername | string | `"postgres"` |  |
