### eupf charts
```bash
helm pull oci://ghcr.io/edgecomllc/charts/eupf --version 0.5.0
```

### open5gs charts
```bash
helm pull oci://registry-1.docker.io/gradiant/open5gs --version 2.1.0

### ueransim charts
helm pull oci://registry-1.docker.io/gradiant/ueransim-gnb --version 0.2.6

#### steps to install 
helm install eupf ./eupf -n open5gs
helm install open5gs ./open5gs -n open5gs
kubectl apply -f ./smf-configmap.yaml -n open5gs
kubectl scale --replicas=1 deployment open5gs-smf -n open5gs
helm install ueransim ./ueransim-gnb -n open5gs