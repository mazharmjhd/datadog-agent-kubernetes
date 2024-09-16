# datadog-agent-kubernetes

need install :

helm repo add datadog https://helm.datadoghq.com
helm repo update

helm install datadog-agent datadog/datadog \
  --set datadog.apiKey=cd7d543b2a3423114accc56e72143a3b \
  --set datadog.appKey=a4f071aea64fd6bbc42516431e9f2fc9f3af1b63 \
  --set datadog.logs.enabled=true \
  --set datadog.logs.containerCollectAll=true \
  --set datadog.volumeMounts[0].name=logdatadog \
  --set datadog.volumeMounts[0].mountPath=/var/log/datadog \
  --set datadog.volumes[0].name=logdatadog \
  --set datadog.volumes[0].emptyDir={}
