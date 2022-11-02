# Kustomize

In order to get the objects that will be created in dev:
```
kustomize build overlays/dev
```

Same for prod:
```
kustomize build overlays/prod
```
In order to override any other object you have to create the yaml file in the correct env and
add this one to `Kustomization.yaml` `patchesStrategicMerge` section.

To apply this to the K8s cluster: 
```
kubectl apply -k overlays/dev
```

# Helm

In order to get the objects that will be created:
```
helm template .
```

To apply this into the current K8s cluster:
```
helm install -f values.yaml helm-demo .
```

Package the chart
```
helm package .
```
 
