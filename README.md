### Kubernetes configuration
* make deployment with config file
> to deploy a replica, run
- kubectl apply -f <deployment file name>

> to deploy a service, run
- kubectl apply -f <service file name>

> To get more details on the pods, run
- kubectl get pods -o wide

* To attach secrets to your deployment, first create the secret
> kubectl apply -f <secret.yml file>
* To create the secret in base 64, run <'echo -n "password' | base64" and "echo -n 'username' | base64">

- Then you reference the secret keys in the deployment file

### demo-k8s-deployment

kubsctl -n qos-demo patch pod qos-demo-pod --patch {"spec":{"containers":[{"name":"", "resource":{"limits":{"cpu":800mi}, "requests":{"cpu":800mi}}}]}}
