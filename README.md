# protectvds
Several Steps For Protection Your VDS

1. Install `apt-get install iptables-persistent`
   - accept saving current list of rules in /etc/iptables/rules.v4 for IPv4 & /etc/iptables/rules.v6 for IPv6
2. Open `rules.v4` and change whole content with file in repo
3. Accept rules via `iptables-restore < /etc/iptables/rules.v4`
4. Check it `iptables -L`