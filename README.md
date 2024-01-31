caddy-tls-dns
=========

An opinionated ansible role for caddy on debian 12 managed by systemd which does a cloudflare dns challenge for tls certificates and forwards to a local port or serves a local path.

Example Playbook
----------------

Requirements.yml

```
- src: https://github.com/tphummel/ansible-role-caddy-tls-dns.git
```

playbook.yml for forwarding to local port
```
    - hosts: servers
      roles:
        - role: ansible-role-caddy-tls-dns
          vars:
            caddy_domain: my-app.mydomain.com
            caddy_tls_email: "tls@mydomain.com"
            caddy_dns_api_token: "my-secret-token"
            caddy_target_port: "8181"
```

playbook.yml for serving a local path as a fileserver
```
    - hosts: servers
      roles:
        - role: ansible-role-caddy-tls-dns
          vars:
            caddy_domain: my-app.mydomain.com
            caddy_tls_email: "tls@mydomain.com"
            caddy_dns_api_token: "my-secret-token"
            caddy_target_path: "/var/www/html"
```

License
-------

MIT
