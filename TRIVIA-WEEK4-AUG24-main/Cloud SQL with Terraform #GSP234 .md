# GSP234
## Run in cloudshell
```cmd
export ZONE=
```
```cmd
mkdir sql-with-terraform
cd sql-with-terraform
gsutil cp -r gs://spls/gsp234/gsp234.zip .
unzip gsp234.zip
sed -i "
/variable \"project\" {/,/}/s/default     = \"\"/default     = \"$PROJECT_ID\"/;
/variable \"region\" {/,/}/s/default     = \"us-central1\"/default     = \"$ZONE\"/
" variables.tf
terraform init
terraform plan -out=tfplan
terraform apply tfplan
```
