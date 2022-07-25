
# K8s Ingress Project -Ynet Parser and Bitcoin Price app
- 

The project goal is to create an Ingress API object that manages external access to two services:
1. Ynet Parser App .
2. Bitcoin Price + Average price .
while they are running in a K8s cluster.

## Run Locally

1. Clone the project
```bash
https://github.com/jumana-abuhattoom/k8sYnetBitcoin.git
```
2. start minikube by running the command:
```bash
minikube start
```
3. Enabble the Ingress Controller :
```bash
minikube addons enable ingress 

```
4. Apply all the yaml files that are attached by running the command: 
```bash
kubectl apply -f .
```
5. run the command
```bash
minikube tunnel
```
-------------------------------------------
Call the API from your browser or using curl at :
1. [http://localhost/bitcoin-price](http://localhost:8000) in order to See the Current BitCoin Price and 
2.  [http://localhost/bitcoin-price/avg](http://localhost:8000/avg) to see the  Average Price in the last 10 minutes.
3. [http://localhost/ynet-news](http://localhost:8000) in order to See Ynet updated news 


---------------------------------------------
In order to stop the deployment run and exit the minikube, run the following commands:
1. press CTRL+C in order to exit the tunnel 
2. run the commands: 
```bash
kubectl delete -f .
```
3. in order to Check that all deployments are deleted Run the command:
```bash
kubectl get all 
```
4. And then : 
```bash
minikube delete 
```
```bash
exit
```
