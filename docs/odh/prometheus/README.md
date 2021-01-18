## Prometheus Access

Prometheus is available at this link: http://prometheus-portal-opf-monitoring.apps.cnv.massopen.cloud/

We use the Prometheus Operator to deploy Prometheus and use k8s resources like
ServiceMonitors and PodMonitors to manage the targets that are scraped by Prometheus.


## Monitoring your services

To add services to monitor in Prometheus see [here](add_monitors.md)
