
#
```
root@kali:~# docker image ls
REPOSITORY             TAG                 IMAGE ID            CREATED             SIZE
vulnerables/web-dvwa   latest              ab0d83586b6e        2 years ago         712MB
```
## 範例 ==> asp.net Core 應用程式 容器化
```
GOOGLE ==> dockerhub asp.net core
https://hub.docker.com/_/microsoft-dotnet-aspnet

docker pull mcr.microsoft.com/dotnet/aspnet

docker run -it --rm -p 8000:80 --name aspnetcore_sample mcr.microsoft.com/dotnet/samples:aspnetapp

http://localhost:8000
```
