# Zabbix Monitoring
This role installs and configures Zabbix Agent & Proxies on Ubuntu based systems.

# Tested Packages & Platforms
- Zabbix Agent
    - Ubuntu 20.04, 22.04
        - 6.0, 6.2, 6.4

- Zabbix Proxy
    - Ubuntu 20.04, 22.04
        - 6.0, 6.2, 6.4

# Example Playbooks
## Zabbix Agent
```yaml
- hosts: zabbix_agent
  vars:
    zabbix_server: "ZABBIX SERVER/PROXY FQDN"
    zabbix_server_active: "ZABBIX SERVER/PROXY FQDN"
    zabbix_host_metadata: "zabbix_agent linux ubuntu"
    zabbix_tls_psk_identity: "YOUR-PSK-IDENTITY"
    zabbix_tls_psk: "YOUR-PSK"
  roles:
    - zabbix/agent/6x
```

## Zabbix Proxy
```yaml
- hosts: zabbix_proxy
  vars:
    zabbix_server: "ZABBIX FQDN"
    zabbix_tls_psk_identity: "YOUR-PSK-IDENTITY"
    zabbix_tls_psk: "YOUR-PSK"
  roles:
    - zabbix/proxy/6x
```