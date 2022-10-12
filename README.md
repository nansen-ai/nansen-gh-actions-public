# Nansen Github Actions Public

This is a collection of re-usable github workflows

(WIP), wait for Anders to review this before re-using! 

## Pre-requisites
 
- Service Account with required permissions:
    - roles/container.developer       
    - roles/iam.serviceAccountTokenCreator    
    - roles/storage.admin      
    - roles/composer.environmentAndStorageObjectAdmin (Composer related workflows)

- [Keyless Auth Set-Up](https://cloud.google.com/blog/products/identity-security/enabling-keyless-authentication-from-github-actions)


Once you have gone through the steps above you should have a service account and a workload id provider which you can set as secrets in your repository. 



## [build-publish-image-gcr.yml](.github/workflows/build-publish-image-gcr.yml)

- reads a version file to get version number 
- builds a docker image 
- pushes to gcr 

## [gke-helm-upgrade.yml](.github/workflows/gke-helm-upgrade.yml)


- takes in the helm release, chart , values , gke_cluster info to upgrade a helm deployment


## [composer-vars-update.yml](.github/workflows/composer-vars-update.yml)


- takes in a json variables file, and composer env details , updates composer variables 

## [gcs-rsync.yml](.github/workflows/gcs-rsync.yml)

- run gsutil rsync with some available flags