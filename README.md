# How it works?

### Clone repo

You should run `git clone` on the server with installed k3s.

### Deploy cert-manager

```bash
kubectl create -f files/charts/cert-manager.yaml 
```

### Create cluster-issuer

```bash
kubectl create -f files/resources/cluster-issuer.yaml
```

### Prepare dex chart

- Provide your domain instead of `dex-demo.***`
- Provide your gitlab app clientId and clientSecret
- In groups set your existing gitlab group
- Deploy chart with the following command

```bash
kubectl create -f files/charts/dex.yaml
```

### Configure k3s

```bash
cp files/k3s-config.yaml /etc/rancher/k3s/k3s.yaml
systemctl restart k3s
```

### Create cluster role binding

```bash
kubectl create -f files/resources/cluster-role-binding.yaml
```

### Try things

TODO: describe how to try auth with kubeconfig and with the browser

