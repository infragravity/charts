# Akumuli Helm Chart

This chart deployes [Akumuli](http://github.com/akumuli/akumuli) time series database to Kubernetes 1.8+
By default, it creates persistent volume for Akumuli storage.

Examples:

```bash
helm install ~/github.com/infragravity/charts/stable/akumuli --name=aku --set persistence.enabled=false
```

The values.yaml file can be also modified to specify resource limits and image tags. 