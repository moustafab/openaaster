# openfaaster

a sample function as a service app using (OpenFaas)[https://docs.openfaas.com/]

## dependencies

1. faas-cli
2. kubernetes
3. docker
4. helm

## getting started

Follow this guide to deploy open-faas to minikube https://medium.com/devopslinks/getting-started-with-openfaas-on-minikube-634502c7acdf

With sample faas-node

1. Set the target docker daemon to minikube `eval $(minikube docker-eval)`
2. Build the function image `faas-cli build -f faas-node.yml`
3. Set the gateway up `export FAAS_GW=$(minikube service --url -n openfaas gateway-external)`
4. Deploy the function `faas-cli deploy -f faas-node.yml --gateway $FAAS_GW`
5. Invoke the function `faas-cli invoke faas-node --gateway $FAAS_GW`
