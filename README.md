# MediaWiki Deployment Using Docker, Jenkins CI/CD, Kubernetes

This Project Deploy Mediawiki Statefulset Application to K8s using Jenkins CI/CD. This Project is divided into three following parts -


## Docker

1. The folder, **docker** contains mediawiki, database Dockerfiles, which will be used to containerize the application.
2. For local testing for Docker, we are using docker-compose.

## Jenkins

We are Jenkins CI/CD to deploy application into the K8s. Jenkinsfile does the following stuff for us.

1. Build the Dockerfile
2. Copies image to AWS ECR
3. Deploy to the EKS

## Kubernetes

The folder **k8s** contains, k8s deployment stuff. This folder contains following stuff for us.

1. Deploy mediawiki app image to k8s
2. Create Namespaces for dev, staging, prod
3. Deploy database images to k8s.

