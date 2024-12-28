# devops-journey

# CKAD (Certified Kubernetes Application Developer)
## Notes on containerization 
### What is the `init container` in kuberentes pod ?
- init containers are basically used when you have a multi-container pod and some containers must run at the beginning of the pod and finished then the other normal containers run after it 
- so we specifiy the normal containers that will always be up and running in the `containers` section and the initial running containers at the `initContainers` section.

### What is the difference between `CMD` and `ENTRYPOINT` in Dockerfile ?
- using the `CMD`, will replace the params in the dockerfile by the params that are passed when you run the container entirely.
- using the `ENTRYPOINT`, the params will be appended to what is already written into the dockerfile
![alt text](image-4.png)

- U can use the CMD with the ENTRYPOINT to provide default values for your params 
![alt text](image-5.png)

- the mapping between the `CMD` and `ENTRYPOINT` in dockerfile to k8s yaml definition : 
![alt text](image-6.png)


## Different status of a POD
![alt text](image-8.png)


## How to reference env vars from config maps : 
![alt text](image-7.png)

## What is the replicaset ?
- used to ensure that we always have the desired number of pods running and up at all time
- used for scalling the loads across multiple instances


## Readiness Probes : 
![alt text](image-9.png)

## Liveness Probes : 
![alt text](image-10.png)

## The Canary Deployment Strategy : 

![alt text](image-11.png)

- we can use a very popular tool like Istio to handle this strategy
- Canary strategy is basically distribute the traffic over the new and old deployments by following these rules : 
    - let the traffic be distributed across both deployments
    - reduce the number of traffic to the new deployment version (in plain k8s without istio, we could simply reduce the number of pods from the new deployment version so it takes less percentage of the traffic) 

--------
# CI/CD using Github Actions

## What is CI/CD ? 
It's a way to automate your development and deployment phases.

![alt text](image.png)

### CI in details : 
![alt text](image-1.png)

### CD in details : 
![alt text](image-2.png)

### The difference between Continuous Delivery and Deployment concepts : 
![alt text](image-3.png)

## What is the workflow ? 
- Automated process for executing tasks.
- All your workflows are located at `.github/workflows/`.
- A Workflow is triggered via an event, so each workflow gets fired when the specific `on` event occured.

## Notes On workflows : 
### your jobs are running on a separate virtual machine `Runner`, so they have no access on your codebase (repo), so you have to allow the job to clone the repo to be able to access the files and folders.