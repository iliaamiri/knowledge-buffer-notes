
## Port forwarding for rds (jumpbox)

explain

```
ssh -vvv -i ~/.ssh/jumpbox -L 5433:<rds-endpoint>:5432 <ec2-username>@<ec2-jumpbox-host>
```

## Forward a port to localhost from remote server
```bash
ssh -i ~/.ssh/id_rsa -p <ssh-port> -L <local-port>:localhost:<forwarded-port> <user>@<host>
```
