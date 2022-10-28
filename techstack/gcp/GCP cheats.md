#gcp #k8s #cheat 

```sh
# list projects
gcloud projects list

# set project
gcloud config set project prj-ligcore-eu-dev-wkuh
# get project
gcloud config get project

# auth
gcloud auth login
gcloud auth login --no-launch-browser

gcloud auth application-default login --no-launch-browser

# list clusters
gcloud container clusters list

# get credentials
gcloud container clusters get-credentials d-eu-west4 --zone=europe-west4

# use context
kubectl config use-context gke_prj-ene-dev-dlbm_europe-west4-b_dev-europe-west4-b
```