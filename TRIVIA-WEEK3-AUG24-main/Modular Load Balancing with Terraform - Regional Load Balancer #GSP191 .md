# GSP191
## Run in cloudshell
```cmd
export REGION=
```
```cmd
git clone https://github.com/GoogleCloudPlatform/terraform-google-lb
cd ~/terraform-google-lb/examples/basic
export GOOGLE_PROJECT=$(gcloud config get-value project)
terraform init
sed -i 's/us-central1/'"$REGION"'/g' variables.tf
echo $GOOGLE_PROJECT | terraform plan
echo $GOOGLE_PROJECT | terraform apply -auto-approve
```
## Wait 5 Minutes
