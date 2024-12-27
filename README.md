### eupf charts
```bash
helm pull oci://ghcr.io/edgecomllc/charts/eupf --version 0.5.0
```

### open5gs charts
```bash
helm pull oci://registry-1.docker.io/gradiant/open5gs --version 2.1.0
```

#### steps to install
```console
make eupf ./eupf -n open5gs
make open5gs ./open5gs -n open5gs
kubectl apply -f ./smf-configmap.yaml -n open5gs
kubectl scale --replicas=1 deployment open5gs-smf -n open5gs
```
