## FlasK8 - A minimal template for setting up Flask REST API in Kubernetes.

### Setup Instruction

* docker build --tag ritesh2000/ml-score-api .

* docker run --rm --name test-api -p 5000:5000 -d ritesh2000/ml-score-api

* curl http://localhost:5000/score \
    --request POST \
    --header "Content-Type: application/json" \
    --data '{"X": [1, 2]}'

* docker push ritesh2000/ml-score-api

* kubectl create deployment ml-score-api --image=ritesh2000/ml-score-api:latest

* kubectl port-forward <pod-name> 5000:5000

* kubectl expose deployment ml-score-api --port 5000 --type=LoadBalancer --name ml-score-api-lb
