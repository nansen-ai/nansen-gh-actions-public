# Nansen Github Actions Public

This is a collection of re-usable github workflows


## [build-publish-image-gcr.yml](.github/workflows/build-publish-image-gcr.yml)

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

