# GSP233
## Run in cloudshell
```cmd
export ZONE=
```
```cmd
export REGION=${ZONE::-2}
gsutil -m cp -r gs://spls/gsp233/* .
cd tf-gke-k8s-service-lb
terraform init
terraform apply -var="region=$REGION" -var="location=$ZONE"  -auto-approve
```
