# Nansen Github Actions Public

This is a collection of re-usable github workflows

(WIP), wait for Anders to review this before re-using! 

## [build-publish-image-gcr.yml](build-publish-image-gcr.yml)

Pre-requisites:
- Service Account with required permissions:
    - roles/container.developer       
    - roles/iam.serviceAccountTokenCreator    
    - roles/storage.admin      
- [Keyless Auth Set-Up](https://cloud.google.com/blog/products/identity-security/enabling-keyless-authentication-from-github-actions)

Once you have gone through the steps above you should have a service account and a workload id provider which you can set as secrets in your repository. 

this workflow simply:
- reads a version file to get version number 
- builds a docker image 
- pushes to gcr 

## [gke-helm-upgrade.yml](gke-helm-upgrade.yml)

Same pre-requisites as the previous action

this workflow simply:
- takes in the helm release, chart , values , gke_cluster info to upgrade a helm deployment