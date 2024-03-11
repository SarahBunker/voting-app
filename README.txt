# sample voting app

## Preparing environment by cleaning up old projects

Locally I am running minikube which I need to start before deploying pods

```bash
minikube start
```

Then I can check for built pods running

```bash
kubectl get pods
```

Remove pods
```bash
kubectl delete pod http-frontend-746f74697-fljpn
# delete all
kubectl delete pods --all
```

I also had a deployment.

```bash
kubectl get deployments
kubectl remove deployment http-frontend
```

checking for other resources deployed like services

```bash 
$ kubectl get all
NAME                 TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
service/kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP   160d
```

Don't delete this service because it is used internally by kubernetes.

## deploying services and pods

use this command to deploy each pod and service

```bash
kubectl create -f FILE_NAME
```

Can view both pods and services like this:

```bash
kubectl get pods,service
# or

kubectl get pods,svc
```

since svc is short for service