# (FreeBSD) AdBlock using dnsmasq

It's just a simple script which creates an include file for dnsmasq. 

# How to use

## dnsmasq configuration

Add a ``conf-file`` entry to your dnsmasq configuration, usually located at ``/usr/local/etc/dnsmasq.conf``.

```
$ grep conf-file /usr/local/etc/dnsmasq.conf
conf-file=/usr/local/share/dnsmasq/trust-anchors.conf
conf-file=/usr/local/etc/dnsmasq.more.conf
```

## How to run the Script

```
$ sh create-dnsmasq-include-file
$ service dnsmasq restart
```

## Rollback

```
$ cp /usr/local/etc/dnsmasq.more.conf{.bak,}
$ service dnsmasq restart
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
| pipes | Source starting with 2 pipes which I use as a separator. Needs special handling. |

# Kudos

Kudos to [notracking](https://github.com/notracking/hosts-blocklists)! The blocklist is based on the work done in this retired project!
Kudos to [RPiList](https://github.com/RPiList)! Adding their blocklists too!
