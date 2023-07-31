# windmill

![Version: 1.6.44](https://img.shields.io/badge/Version-1.6.44-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.135.0](https://img.shields.io/badge/AppVersion-1.135.0-informational?style=flat-square)

Windmill - Turn scripts into endpoints, workflows and UIs in minutes

**Homepage:** <https://www.windmill.dev/>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| windmill | <ruben@windmill.dev> | <https://www.windmill.dev/> |

## Source Code

* <https://github.com/windmill-labs/windmill-helm-charts.git>

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | minio | 12.4.2 |
| https://charts.bitnami.com/bitnami | postgresql | 12.3.1 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| enterprise.enabled | bool | `false` | enable Windmill Enterprise , requires license key. |
| enterprise.enabledS3DistributedCache | bool | `false` |  |
| enterprise.licenseKey | string | `"123456F"` | Windmill provided Enterprise license key. Sets LICENSE_KEY environment variable in app and worker container. |
| enterprise.nsjail | bool | `false` | use nsjail for sandboxing |
| enterprise.s3CacheBucket | string | `"mybucketname"` | S3 bucket to use for dependency cache. Sets S3_CACHE_BUCKET environment variable in worker container |
| enterprise.samlMetadata | string | `""` | SAML Metadata URL to enable SAML SSO |
| enterprise.scimToken | string | `""` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `true` | enable/disable included ingress resource |
| ingress.tls | list | `[]` | TLS config for the ingress resource. Useful when using cert-manager and nginx-ingress |
| minio.auth.rootPassword | string | `"windmill"` |  |
| minio.auth.rootUser | string | `"windmill"` |  |
| minio.enabled | bool | `false` | enabled included Minio operator for s3 resource demo purposes |
| minio.fullnameOverride | string | `"windmill-minio"` |  |
| minio.mode | string | `"standalone"` |  |
| minio.primary.enabled | bool | `true` |  |
| postgresql.auth.database | string | `"windmill"` |  |
| postgresql.auth.postgresPassword | string | `"windmill"` |  |
| postgresql.enabled | bool | `true` | enabled included Postgres container for demo purposes only using bitnami |
| postgresql.fullnameOverride | string | `"windmill-postgresql"` |  |
| postgresql.primary.persistence.enabled | bool | `true` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| windmill.app.affinity | object | `{}` | Affinity rules to apply to the pods |
| windmill.app.annotations | object | `{}` | Annotations to apply to the pods |
| windmill.app.autoscaling.enabled | bool | `false` | enable or disable autoscaling |
| windmill.app.autoscaling.maxReplicas | int | `10` | maximum autoscaler replicas |
| windmill.app.autoscaling.targetCPUUtilizationPercentage | int | `80` | target CPU utilization |
| windmill.app.extraEnv | list | `[]` | Extra environment variables to apply to the pods |
| windmill.app.nodeSelector | object | `{}` | Node selector to use for scheduling the pods |
| windmill.app.resources | object | `{}` | Resource limits and requests for the pods |
| windmill.app.tolerations | list | `[]` | Tolerations to apply to the pods |
| windmill.appReplicas | int | `2` | replica for the application app |
| windmill.baseDomain | string | `"windmill"` | domain as shown in browser, this variable and `baseProtocol` are used as part of the BASE_URL environment variable in app and worker container and in the ingress resource, if enabled |
| windmill.baseProtocol | string | `"http"` | protocol as shown in browser, change to https etc based on your endpoint/ingress configuration, this variable and `baseDomain` are used as part of the BASE_URL environment variable in app and worker container |
| windmill.cookieDomain | string | `""` | domain to use for the cookies. Use it if windmill is hosted on a subdomain and you need to share the cookies with the hub for instance |
| windmill.createWorkspaceRequireSuperadmin | bool | `false` | is any user allowed to create workspaces |
| windmill.databaseUrl | string | `"postgres://postgres:windmill@windmill-postgresql/windmill?sslmode=disable"` | Postgres URI, pods will crashloop if database is unreachable, sets DATABASE_URL environment variable in app and worker container |
| windmill.databaseUrlSecretName | string | `""` | name of the secret storing the database URI, take precedence over databaseUrl. The key of the url is 'url' |
| windmill.exposeHostDocker | bool | `false` | mount the docker socket inside the container to be able to run docker command as docker client to the host docker daemon |
| windmill.globalErrorHandlerPath | string | `""` | if set, the path to a script in the admins workspace that will be triggered upon any jobs failure |
| windmill.image | string | `""` | windmill image tag, will use the Acorresponding ee or ce image from ghcr if not defined. Do not include tag in the image name. |
| windmill.instanceEventsWebhook | string | `""` | send instance events to a webhook. Can be hooked back to windmill |
| windmill.lsp.affinity | object | `{}` | Affinity rules to apply to the pods |
| windmill.lsp.annotations | object | `{}` | Annotations to apply to the pods |
| windmill.lsp.autoscaling.enabled | bool | `false` | enable or disable autoscaling |
| windmill.lsp.autoscaling.maxReplicas | int | `10` | maximum autoscaler replicas |
| windmill.lsp.autoscaling.targetCPUUtilizationPercentage | int | `80` | target CPU utilization |
| windmill.lsp.extraEnv | list | `[]` | Extra environment variables to apply to the pods |
| windmill.lsp.nodeSelector | object | `{}` | Node selector to use for scheduling the pods |
| windmill.lsp.resources | object | `{}` | Resource limits and requests for the pods |
| windmill.lsp.tag | string | `"latest"` |  |
| windmill.lsp.tolerations | list | `[]` | Tolerations to apply to the pods |
| windmill.lspReplicas | int | `2` | replicas for the lsp containers used by the app |
| windmill.multiplayer.affinity | object | `{}` | Affinity rules to apply to the pods |
| windmill.multiplayer.annotations | object | `{}` | Annotations to apply to the pods |
| windmill.multiplayer.autoscaling.enabled | bool | `false` | enable or disable autoscaling |
| windmill.multiplayer.autoscaling.maxReplicas | int | `10` | maximum autoscaler replicas |
| windmill.multiplayer.autoscaling.targetCPUUtilizationPercentage | int | `80` | target CPU utilization |
| windmill.multiplayer.extraEnv | list | `[]` | Extra environment variables to apply to the pods |
| windmill.multiplayer.nodeSelector | object | `{}` | Node selector to use for scheduling the pods |
| windmill.multiplayer.resources | object | `{}` | Resource limits and requests for the pods |
| windmill.multiplayer.tag | string | `"latest"` |  |
| windmill.multiplayer.tolerations | list | `[]` | Tolerations to apply to the pods |
| windmill.multiplayerReplicas | int | `2` | replicas for the lsp containers used by the app |
| windmill.npmConfigRegistry | string | `""` | pass the npm for private registries |
| windmill.numWorkers | int | `1` | workers per worker container, default and recommended is 1 to isolate one process per container, sets NUM_WORKER environment variable for worker container.  app container has 0 NUM_WORKERS by default |
| windmill.oauthConfig | string | `"{}\n"` | raw oauth config. See https://docs.windmill.dev/docs/misc/setup_oauth |
| windmill.oauthSecretName | string | `""` | name of the secret storing the oauthConfig. See https://docs.windmill.dev/docs/misc/setup_oauth |
| windmill.pipExtraIndexUrl | string | `""` | pass the extra index url to pip for private registries |
| windmill.pipIndexUrl | string | `""` | pass the index url to pip for private registries |
| windmill.pipTrustedHost | string | `""` | pass the trusted host to pip for private registries |
| windmill.rustLog | string | `"info"` | rust log level, set to debug for more information etc, sets RUST_LOG environment variable in app and worker container |
| windmill.smtp | object | `{"enabled":false,"from":"noreply@windmill.dev","host":"smtp.gmail.com","password":"bar","port":587,"tls_implicit":false,"username":"ruben@windmill.dev"}` | set smtp configs for windmill to be able to send emails when adding users to instance and workspaces |
| windmill.tag | string | `""` | windmill app image tag, will use the App version if not defined |
| windmill.workerGroups[0].affinity | object | `{}` | Affinity rules to apply to the pods |
| windmill.workerGroups[0].annotations | object | `{}` | Annotations to apply to the pods |
| windmill.workerGroups[0].extraEnv | list | `[]` | Extra environment variables to apply to the pods |
| windmill.workerGroups[0].name | string | `"gpu"` |  |
| windmill.workerGroups[0].nodeSelector | object | `{}` | Node selector to use for scheduling the pods |
| windmill.workerGroups[0].replicas | int | `0` |  |
| windmill.workerGroups[0].resources | object | `{}` | Resource limits and requests for the pods |
| windmill.workerGroups[0].tolerations | list | `[]` | Tolerations to apply to the pods |
| windmill.workerReplicas | int | `2` | replicas for the workers, jobs are executed on the workers |
| windmill.workers.affinity | object | `{}` | Affinity rules to apply to the pods |
| windmill.workers.annotations | object | `{}` | Annotations to apply to the pods |
| windmill.workers.autoscaling.enabled | bool | `false` | will not benefit from the global cache and the performances will be poor for newly spawned pods |
| windmill.workers.autoscaling.maxReplicas | int | `10` | maximum autoscaler replicas |
| windmill.workers.autoscaling.targetCPUUtilizationPercentage | int | `80` | target CPU utilization |
| windmill.workers.extraEnv | list | `[]` | Extra environment variables to apply to the pods |
| windmill.workers.nodeSelector | object | `{}` | Node selector to use for scheduling the pods |
| windmill.workers.resources | object | `{}` | Resource limits and requests for the pods |
| windmill.workers.tolerations | list | `[]` | Tolerations to apply to the pods |

## Keeping the PostgreSQL password secret

If you would prefer to keep the PostgreSQL password or connection string out of the Helm values, there are two different possible approaches:

1. Use `windmill.databaseUrlSecretName` to point at a Secret with a `url` key containing the entire database connection string.

2. Use `windmill.databaseUrl` with [Dependent Environment Variables](https://kubernetes.io/docs/tasks/inject-data-application/define-interdependent-environment-variables/) together with `windmill.app.extraEnv` and `windmill.workers.extraEnv`.

An example of the second approach might use Helm values similar to this:

```yaml
windmill:
  databaseUrl: "postgres://windmill:$(DATABASE_PASSWORD)@windmill-postgres/windmill?sslmode=require"

  workers:
    extraEnv:
    - name: DATABASE_PASSWORD
      valueFrom:
        secretKeyRef:
          name: windmill-postgres
          key: password

  app:
    extraEnv:
    - name: DATABASE_PASSWORD
      valueFrom:
        secretKeyRef:
          name: windmill-postgres
          key: password
```

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
