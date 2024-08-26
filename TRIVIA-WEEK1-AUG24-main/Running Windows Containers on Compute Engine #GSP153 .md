# GSP153
## Connect to RDP By going to `COMPUTE ENGINE` > `VM INSTANCE` > Click `RDP`
## Open the file and fill the username as `demouser` and passowrd `P@ssw0rd`
## Once Connected `Run Command Prompt as administrator`
## Run the following commands 
```cmd
mkdir my-windows-app
cd my-windows-app
mkdir content
call > content\index.html
(
echo ^<html^>
echo   ^<head^>
echo     ^<title^>Windows containers^</title^>
echo   ^</head^>
echo   ^<body^>
echo     ^<p^>Windows containers are cool!^</p^>
echo   ^</body^>
echo ^</html^>
) > content\index.html
call > Dockerfile
echo FROM mcr.microsoft.com/windows/servercore/iis:windowsservercore-ltsc2019 > Dockerfile
echo RUN powershell -NoProfile -Command Remove-Item -Recurse C:\inetpub\wwwroot\* >> Dockerfile
echo WORKDIR /inetpub/wwwroot >> Dockerfile
echo COPY content/ . >> Dockerfile
docker build -t gcr.io/dotnet-atamel/iis-site-windows .
```
