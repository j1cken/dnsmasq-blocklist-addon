# (FreeBSD) AdBlock using dnsmasq

It's just a simple script which creates an include file for dnsmasq. 

# How to use

```
sh create-dnsmasq-include-file
echo "restart dnsmasq? Ctrl-C to cancel ..."
read myarg
service dnsmasq restart
```

## Rollback

```
cp /usr/local/etc/dnsmasq.more.conf{.bak,}
service dnsmasq restart
```

# Blocklist Pattern

| Pattern | Source  | Type    | Category |
| ------- | ------- | ------- | -------  |
| RegEx to parse the Source | URL to download the domains to be blocked | not used | not used |

## Special RegEx

| Pattern | Meaning |
| ------- | ------- |
| NXDOMAIN | Source entry skipped |
| csv | Source parsed as comma separated values |

# Kudos

Kudos to [notracking](https://github.com/notracking/hosts-blocklists)! The blocklist is based on the work done in this retired project!
