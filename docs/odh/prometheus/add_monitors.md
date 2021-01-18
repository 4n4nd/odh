# Add Prometheus ServiceMonitors

## Add Roles and RoleBindings
For the Operate First Prometheus to be able to access your services, we need to
give service access to the Prometheus serviceaccount (`prometheus-k8s`).

To do this, we need to create a Role that defines the resources Prometheus needs access to and a RoleBinding that provides this access to the Prometheus serviceaccount.

In
To monitor applications, we use ServiceMonitor resources from the Prometheus Operator.

link [test](/odh/overlays/moc/monitoring/servicemonitors/observatorium-servicemonitor.yaml)
