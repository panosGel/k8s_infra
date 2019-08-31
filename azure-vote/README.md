# azure-vote 
Using the azure vote app to play around with services and deployments

Source code for the actual app:

https://github.com/Azure-Samples/azure-voting-app-redis

## Creating the deployments & services

`kubectl apply -f deployments/<file>`
`kubectl apply -f services/<files>`


## Viewing the ingress

`kubectl describe services azure-vote-front`

## Accessing the app

`kubectl proxy`

Use then the ingress ip given from the load balancer

## Cleaning up

`kubectl delete service azure-vote-back azure-vote-front`
`kubectl delete service azure-vote-back azure-vote-front`