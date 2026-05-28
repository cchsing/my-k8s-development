

```
helm install opentelemetry-operator open-telemetry/opentelemetry-operator \
--set "manager.collectorImage.repository=ghcr.io/open-telemetry/opentelemetry-collector-releases/opentelemetry-collector-k8s" \
--set admissionWebhooks.certManager.enabled=false \
--set admissionWebhooks.autoGenerateCert.enabled=true

helm show values open-telemetry/opentelemetry-operator
```