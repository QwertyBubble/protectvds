# protectvds
Several Steps For Protection Your VDS (against bots/scanners/kiddis)

1. Change port ssh 22/TCP to smth different in configuration file `/etc/sshd/sshd_config` (and don't forget to restart ssh daemon)
2. Install `apt-get install fail2ban` service
   - look at `/etc/fail2ban/jail.conf` for tuning some settings
   - as idea: can we use suspicious User-Agents from [Ultimate Bad Bot Blocker Project](https://github.com/mitchellkrogza/apache-ultimate-bad-bot-blocker/blob/master/_generator_lists/bad-user-agents.list) in http/https regex conditions in this file?
3. Iptables configuration
   - install `apt-get install iptables-persistent`
   - accept saving current list of rules in `/etc/iptables/rules.v4` for IPv4 & `/etc/iptables/rules.v6` for IPv6
   - open `rules.v4` and change whole content with file in this repo
   - accept rules via `iptables-restore < /etc/iptables/rules.v4`
   - check it `iptables -L`