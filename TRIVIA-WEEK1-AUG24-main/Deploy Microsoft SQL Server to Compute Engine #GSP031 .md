# GSP031
## Run in cloudshell
```cmd
export ZONE=
```
```cmd
gcloud compute instances create sqlserver-lab \
--zone=$ZONE \
--image=projects/windows-sql-cloud/global/images/sql-2016-web-windows-2016-dc-v20240711 \
--machine-type=e2-medium \
--boot-disk-size=50GB \
--boot-disk-type=pd-ssd
echo y | gcloud compute reset-windows-password sqlserver-lab --zone=$ZONE
```
