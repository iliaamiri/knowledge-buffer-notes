```bash
# list the table with line numbers
sudo iptables -L INPUT --line-numbers -n

# allow the port access for a certain ip (before the line number
sudo iptables -I INPUT <line-number> -p tcp -s <whitelisted-ip> --dport <port-number> -j ACCEPT
```
