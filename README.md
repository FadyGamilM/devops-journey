# devops-journey

# CKAD (Certified Kubernetes Application Developer)


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