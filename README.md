# cert-manager-k8s
deploy cert manager for k8s cluster using yaml file

Check latest version here

https://github.com/cert-manager/cert-manager/releases

I use cert-manager version  0.14

https://github.com/cert-manager/cert-manager/releases/download/v1.7.1/cert-manager.yaml



#Install cert-manager for ssl

Edit your email insde letsencrypt-issuer.yaml
```

kubectl apply -f cert-manager1-7.yaml


kubectl apply -f letsencrypt-issuer.yaml 
```

to check 

` kubectl get clusterissuers `

to check logs when you create ssl 

` kubectl logs -f clusterissuers letsencrypt-prod `

To let ingress user our Cluster Issuer

edit you ingress yaml file and add these lines 

```
  annotations:
    cert-manager.io/cluster-issuer: letsencrypt-prod
    kubernetes.io/ingress.class: nginx

```

