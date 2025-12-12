# simple-krr-dashboard

A Helm chart to deploy Simple KRR Dashboard

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| ialejandro | <hello@ialejandro.rocks> | <https://ialejandro.rocks> |

## Prerequisites

* Helm 3+

## Add repository

```console
helm repo add simple-krr-dashboard https://devops-ia.github.io/helm-simple-krr-dashboard
helm repo update
```

## Install Helm chart (repository mode)

```console
helm install [RELEASE_NAME] simple-krr-dashboard/simple-krr-dashboard
```

This install all the Kubernetes components associated with the chart and creates the release.

_See [helm install](https://helm.sh/docs/helm/helm_install/) for command documentation._

## Install Helm chart (OCI mode)

Charts are also available in OCI format. The list of available charts can be found [here](https://github.com/devops-ia/helm-simple-krr-dashboard/pkgs/container/helm-simple-krr-dashboard%2Fsimple-krr-dashboard).

```console
helm install [RELEASE_NAME] oci://ghcr.io/devops-ia/helm-simple-krr-dashboard/simple-krr-dashboard --version=[version]
```

## Uninstall Helm chart

```console
helm uninstall [RELEASE_NAME]
```

This removes all the Kubernetes components associated with the chart and deletes the release.

_See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation._

## Examples

See [examples](./examples) directory.

## Configuration

See [Customizing the chart before installing](https://helm.sh/docs/intro/using_helm/#customizing-the-chart-before-installing). To see all configurable options with comments:

```console
helm show values simple-krr-dashboard/simple-krr-dashboard
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity for pod assignment </br> Ref: https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/#affinity-and-anti-affinity |
| annotations | object | `{}` | Configure annotations on Deployment |
| args | list | `[]` | Configure args </br> Ref: https://kubernetes.io/docs/tasks/inject-data-application/define-command-argument-container/ |
| autoscaling | object | `{"enabled":false,"maxReplicas":100,"minReplicas":1,"targetCPUUtilizationPercentage":80}` | Autoscaling with CPU or memory utilization percentage </br> Ref: https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/ |
| command | list | `[]` | Configure command </br> Ref: https://kubernetes.io/docs/tasks/inject-data-application/define-command-argument-container/ |
| configMaps | object | `{}` | ConfigMap values to create configuration files Generate ConfigMap with following name: <release-name>-<name> </br> Ref: https://kubernetes.io/docs/concepts/configuration/configmap/ |
| dnsConfig | object | `{}` | Configure DNS </br> Ref: https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/ |
| dnsPolicy | string | `"ClusterFirst"` | Configure DNS policy Options: ClusterFirst, Default, ClusterFirstWithHostNet, None </br> Ref: https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/ |
| env | object | `{}` | Environment variables to configure application </br> Ref: https://github.com/devops-ia/simple-krr-dashboard?tab=readme-ov-file#environment-variables |
| envFromConfigMap | object | `{}` | Variables from configMap |
| envFromFiles | list | `[]` | Variables from files managed by you </br> Ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/#configure-all-key-value-pairs-in-a-configmap-as-container-environment-variables |
| envFromSecrets | object | `{}` | Variables from secrets |
| fullnameOverride | string | `""` | String to fully override simple-krr-dashboard.fullname template |
| hostAliases | list | `[]` | Configure hostAliases </br> Ref: https://kubernetes.io/docs/tasks/network/customize-hosts-file-for-pods/ |
| image | object | `{"pullPolicy":"IfNotPresent","repository":"ghcr.io/devops-ia/simple-krr-dashboard","tag":""}` | Image registry The image configuration for the base service |
| imagePullSecrets | list | `[]` | Docker registry secret names as an array |
| ingress | object | `{"annotations":{},"className":"","enabled":false,"hosts":[{"host":"chart-example.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | Ingress configuration to expose app </br> Ref: https://kubernetes.io/docs/concepts/services-networking/ingress/ |
| initContainers | list | `[]` | Configure additional containers </br> Ref: https://kubernetes.io/docs/concepts/workloads/pods/init-containers/ |
| job | object | `{"affinity":{},"annotations":{},"args":[],"backoffLimit":1,"backoffLimitPerIndex":1,"command":["/bin/bash","-c"],"completionMode":"Indexed","completions":1,"concurrencyPolicy":"Forbid","dnsConfig":{},"dnsPolicy":"ClusterFirst","enabled":true,"env":{},"envFromConfigMap":{},"envFromFiles":[],"envFromSecrets":{},"failedJobsHistoryLimit":1,"image":{"pullPolicy":"IfNotPresent","repository":"robustadev/krr","tag":"v1.27.0"},"initialJob":true,"krrExtraArguments":"","kubectlVersion":"stable","labels":{},"maxFailedIndexes":1,"nodeSelector":{},"parallelism":1,"podAnnotations":{},"podLabels":{},"resources":{},"restartPolicy":"Never","schedule":"0 0 * * *","successfulJobsHistoryLimit":1,"terminationGracePeriodSeconds":30,"tolerations":[],"volumeMounts":[],"volumes":[]}` | CronJob configuration (also used by initial Job if enabled) </br> Ref: https://kubernetes.io/docs/concepts/workloads/controllers/cron-jobs/ |
| job.affinity | object | `{}` | Affinity for the job |
| job.annotations | object | `{}` | Annotations for the job |
| job.args | list | `[]` | Arguments for the job container |
| job.backoffLimit | int | `1` | Number of retries before marking job as failed |
| job.backoffLimitPerIndex | int | `1` | Number of retries per index before marking job as failed |
| job.command | list | `["/bin/bash","-c"]` | Command for the job container |
| job.completionMode | string | `"Indexed"` | Completion mode for the job |
| job.completions | int | `1` | Number of completions required for the job |
| job.concurrencyPolicy | string | `"Forbid"` | Concurrency policy for the cronjob |
| job.dnsConfig | object | `{}` | Configure DNS |
| job.dnsPolicy | string | `"ClusterFirst"` | Configure DNS policy |
| job.enabled | bool | `true` | Enable or disable the cronjob |
| job.env | object | `{}` | Environment variables to configure the job |
| job.envFromConfigMap | object | `{}` | Variables from configMap |
| job.envFromFiles | list | `[]` | Variables from files managed by you |
| job.envFromSecrets | object | `{}` | Variables from secrets |
| job.failedJobsHistoryLimit | int | `1` | Number of failed jobs to keep |
| job.image | object | `{"pullPolicy":"IfNotPresent","repository":"robustadev/krr","tag":"v1.27.0"}` | Image configuration for the job |
| job.initialJob | bool | `true` | Enable or disable the initial job |
| job.kubectlVersion | string | `"stable"` | Version of kubectl to install (use "stable" for latest stable version) |
| job.labels | object | `{}` | Labels for the job |
| job.maxFailedIndexes | int | `1` | Maximum number of failed indexes |
| job.nodeSelector | object | `{}` | Node selector for the job |
| job.parallelism | int | `1` | Number of parallel jobs |
| job.podAnnotations | object | `{}` | Pod annotations for the job |
| job.podLabels | object | `{}` | Pod labels for the job |
| job.resources | object | `{}` | Resource limits and requests for the job |
| job.restartPolicy | string | `"Never"` | Restart policy for the job |
| job.schedule | string | `"0 0 * * *"` | The schedule in Cron format |
| job.successfulJobsHistoryLimit | int | `1` | Number of successful jobs to keep |
| job.terminationGracePeriodSeconds | int | `30` | Termination grace period in seconds |
| job.tolerations | list | `[]` | Tolerations for the job |
| job.volumeMounts | list | `[]` | Volume mounts for the job |
| job.volumes | list | `[]` | Volumes for the job |
| labels | object | `{}` | Configure labels on Deployment |
| lifecycle | object | `{}` | Configure lifecycle hooks </br> Ref: https://kubernetes.io/docs/concepts/containers/container-lifecycle-hooks/ </br> Ref: https://learnk8s.io/graceful-shutdown |
| livenessProbe | object | `{"enabled":false,"failureThreshold":3,"initialDelaySeconds":180,"periodSeconds":10,"successThreshold":1,"timeoutSeconds":5}` | Configure liveness checker </br> Ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/#define-startup-probes |
| livenessProbeCustom | object | `{}` | Custom livenessProbe |
| nameOverride | string | `""` | String to partially override simple-krr-dashboard.fullname template (will maintain the release name) |
| networkPolicy | object | `{"egress":[],"enabled":false,"ingress":[],"policyTypes":[]}` | NetworkPolicy configuration </br> Ref: https://kubernetes.io/docs/concepts/services-networking/network-policies/ |
| networkPolicy.enabled | bool | `false` | Enable or disable NetworkPolicy |
| networkPolicy.policyTypes | list | `[]` | Policy types |
| nodeSelector | object | `{}` | Node labels for pod assignment </br> Ref: https://kubernetes.io/docs/concepts/scheduling-eviction/assign-pod-node/#nodeselector |
| persistentVolume | object | `{"accessModes":["ReadWriteOnce"],"annotations":{},"enabled":false,"labels":{},"selector":{},"size":"8Gi","storageClass":"","volumeBindingMode":"","volumeName":""}` | Persistent Volume configuration </br> Ref: https://kubernetes.io/docs/concepts/storage/persistent-volumes/ |
| persistentVolume.accessModes | list | `["ReadWriteOnce"]` | Persistent Volume access modes Must match those of existing PV or dynamic provisioner </br> Ref: http://kubernetes.io/docs/user-guide/persistent-volumes/ |
| persistentVolume.annotations | object | `{}` | Persistent Volume annotations |
| persistentVolume.enabled | bool | `false` | Enable or disable persistence |
| persistentVolume.labels | object | `{}` | Persistent Volume labels |
| persistentVolume.selector | object | `{}` | Persistent Volume Claim Selector Useful if Persistent Volumes have been provisioned in advance </br> Ref: https://kubernetes.io/docs/concepts/storage/persistent-volumes/#selector |
| persistentVolume.size | string | `"8Gi"` | Persistent Volume size |
| persistentVolume.storageClass | string | `""` | Persistent Volume Storage Class If defined, storageClassName: <storageClass> If set to "-", storageClassName: "", which disables dynamic provisioning If undefined (the default) or set to null, no storageClassName spec is   set, choosing the default provisioner.  (gp2 on AWS, standard on   GKE, AWS & OpenStack) |
| persistentVolume.volumeBindingMode | string | `""` | Persistent Volume Binding Mode If defined, volumeBindingMode: <volumeBindingMode> If undefined (the default) or set to null, no volumeBindingMode spec is set, choosing the default mode. |
| persistentVolume.volumeName | string | `""` | Persistent Volume Name Useful if Persistent Volumes have been provisioned in advance and you want to use a specific one |
| podAnnotations | object | `{}` | Configure annotations on Pods |
| podDisruptionBudget | object | `{"enabled":false,"maxUnavailable":1,"minAvailable":null}` | Pod Disruption Budget </br> Ref: https://kubernetes.io/docs/reference/kubernetes-api/policy-resources/pod-disruption-budget-v1/ |
| podLabels | object | `{}` | Configure labels on Pods |
| podSecurityContext | object | `{}` | Defines privilege and access control settings for a Pod </br> Ref: https://kubernetes.io/docs/concepts/security/pod-security-standards/ </br> Ref: https://kubernetes.io/docs/tasks/configure-pod-container/security-context/ |
| readinessProbe | object | `{"enabled":false,"failureThreshold":3,"initialDelaySeconds":10,"periodSeconds":10,"successThreshold":1,"timeoutSeconds":1}` | Configure readinessProbe checker </br> Ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/#define-startup-probes |
| readinessProbeCustom | object | `{}` | Custom readinessProbe |
| replicaCount | int | `1` | Number of replicas Specifies the number of replicas for the service |
| resources | object | `{}` | Resources limits and requested </br> Ref: https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/ |
| secrets | list | `[]` | Secrets values to create credentials and reference by envFromSecrets Generate Secret with following name: <release-name>-<name> </br> Ref: https://kubernetes.io/docs/concepts/configuration/secret/ |
| securityContext | object | `{}` | Defines privilege and access control settings for a Container </br> Ref: https://kubernetes.io/docs/concepts/security/pod-security-standards/ </br> Ref: https://kubernetes.io/docs/tasks/configure-pod-container/security-context/ |
| service | object | `{"annotations":{},"appProtocol":"HTTP","extraPorts":[],"labels":{},"loadBalancer":{},"port":80,"portName":"http","protocol":"TCP","targetPort":8080,"type":"ClusterIP"}` | Kubernetes service to expose Pod </br> Ref: https://kubernetes.io/docs/concepts/services-networking/service/ |
| service.annotations | object | `{}` | Annotations for the service |
| service.appProtocol | string | `"HTTP"` | Application protocol (HTTP, HTTPS, etc.) |
| service.extraPorts | list | `[]` | Pod extra ports |
| service.labels | object | `{}` | Additional labels for the service |
| service.loadBalancer | object | `{}` | LoadBalancer specific configuration |
| service.port | int | `80` | Kubernetes Service port |
| service.portName | string | `"http"` | Name for the service port |
| service.protocol | string | `"TCP"` | Protocol for the service port |
| service.targetPort | int | `8080` | Pod expose port |
| service.type | string | `"ClusterIP"` | Kubernetes Service type. Allowed values: NodePort, LoadBalancer, ClusterIP, ExternalName |
| serviceAccount | object | `{"annotations":{},"automount":true,"create":true,"name":""}` | Enable creation of ServiceAccount </br> Ref: https://kubernetes.io/docs/concepts/security/service-accounts/ |
| startupProbe | object | `{"enabled":false,"failureThreshold":30,"initialDelaySeconds":180,"periodSeconds":10,"successThreshold":1,"timeoutSeconds":5}` | Configure startupProbe checker </br> Ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/#define-startup-probes |
| startupProbeCustom | object | `{}` | Custom startupProbe |
| strategy | object | `{}` | Configure strategy for the deployment |
| terminationGracePeriodSeconds | int | `30` | Configure Pod termination grace period </br> Ref: https://kubernetes.io/docs/concepts/workloads/pods/pod-lifecycle/#pod-termination |
| testConnection | object | `{"enabled":false,"repository":"busybox","tag":""}` | Enable or disable test connection |
| tolerations | list | `[]` | Tolerations for pod assignment </br> Ref: https://kubernetes.io/docs/concepts/scheduling-eviction/taint-and-toleration/ |
| topologySpreadConstraints | list | `[]` | Control how Pods are spread across your cluster </br> Ref: https://kubernetes.io/docs/concepts/scheduling-eviction/topology-spread-constraints/#example-multiple-topologyspreadconstraints |
| volumeMounts | list | `[]` | Additional volumeMounts on the output Deployment definition |
| volumes | list | `[]` | Additional volumes on the output Deployment definition </br> Ref: https://kubernetes.io/docs/concepts/storage/volumes/ </br> Ref: https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/ </br> Ref: https://kubernetes.io/docs/tasks/inject-data-application/distribute-credentials-secure/#create-a-pod-that-has-access-to-the-secret-data-through-a-volume |
