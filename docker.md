explain
## Copy folder from SSH to host

```shell
scp -r user@your.server.example.com:/path/to/foo /home/user/Desktop/

scp -i C:\Users\User\.ssh\id_rsa -P 9011 -r <user>@<host>:/home/<path>/*.png 'M:/downloads'
```

## Copy from Docker container 

```shell
docker cp :/file/path/within/container /host/path/target
```

---
## Shrink WSL2 virtual disk (Windows only)

**IMPORTANT**: Turn on ALL the docker containers you don't wish to delete

cleanse your computer's soul
```
docker system prune -a --volumes
docker builder prune --all -f
```

1. Open Powershell as Admin
2. Shutdown WSL2
```sh
wsl --shutdown
```
3. Run
```sh
Optimize-VHD -Path "C:\Users\KINGREDBOLDER\AppData\Local\Docker\wsl\disk\docker_data.vhdx" -Mode Full
```