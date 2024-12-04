
## Port forwarding for rds (jumpbox)

explain

```
ssh -vvv -i ~/.ssh/jumpbox -L 5433:<rds-endpoint>:5432 <ec2-username>@<ec2-jumpbox-host>
```


