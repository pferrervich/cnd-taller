# Voting App deployed with raw Kubernetes manifests

This example shows how to leverage [okteto](https://okteto.com) to build Docker's [Voting App](https://github.com/dockersamples/example-voting-app) directly in the cluster. This example is deployed using raw Kubernetes manifests.

This example works in any Kubernetes cluster. Cloud Native Development provides more value in remote Kubernetes clusters, but in order to make it simple to follow this guide, we recommend to use Docker for Mac (with Kubernetes support) or [minikube](https://github.com/kubernetes/minikube). 

## Deploy the Voting App

Clone this repository and move to this example folder.

```console
git clone https://github.com/okteto/samples
cd samples/python-kubectl
```

Run the Voting App by executing:

```console
kubectl apply -f manifests
```
Wait for one or two minutes until the application is running.

## Develop as a Cloud Native Developer

In order to activate your Cloud Native Development, execute:

```console
cd vote
okteto up
```

The `okteto up` command will start a remote development environment that automatically synchronizes and applies your code changes without rebuilding containers (eliminating the **docker build/push/pull/redeploy** cycle).

You can configure Okteto to [automatically start forwarding ports](https://okteto.com/docs/reference/manifest/index.html#forward) from your dev container to your local machine. This sample is already configured like that. You can access the application by opening your browser and going to `http://localhost:8080`.

Edit the file `vote/app.py` and change the `option_a` in line 8 from "Cats" to "Otters". Save your changes.

Finally, refresh the Voting App UI, and cool! your code changes are live!

*review [okteto's usage](https://okteto.com/docs/reference/cli) guide to see other commands available to help you speed you up your development.*

## Cleanup

Cancel the `okteto up` command by pressing `ctrl + c` and run the following command to deactivate the cloud native environment:

```console
okteto down
``` 

Run the following command to remove the resources created by this guide: 

```console
kubectl delete -f manifests
```



