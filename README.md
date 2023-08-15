# Ansible-role-mailu

[![Ansible-role-mailu](https://img.shields.io/ansible/role/56353?label=Role%20Name&logo=ansible&style=flat-square)](https://galaxy.ansible.com/justin_p/mailu)
[![Ansible Quality Score](https://img.shields.io/ansible/quality/56353?label=Ansible%20Quality%20Score&logo=ansible&style=flat-square)](https://galaxy.ansible.com/justin_p/mailu)
[![Ansible Role Downloads](https://img.shields.io/ansible/role/d/56353?label=Ansible%20Role%20Downloads&logo=ansible&style=flat-square)](https://galaxy.ansible.com/justin_p/mailu)
[![Github Actions](https://img.shields.io/github/workflow/status/justin-p/ansible-role-mailu/CI?label=Github%20Actions&logo=github&style=flat-square)](https://github.com/justin-p/ansible-role-mailu/actions)

Ansible role for Mailu. Mailu is a simple yet full-featured mail server as a set of Docker images.

## Requirements

docker and docker-compose should be setup on the host.

## Variables

`defaults/main.yml`

| Variable                            | description                                                                | default value                                                                              |
| ----------------------------------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| mailu_install_path                  | Path to install mailu under                                                | "/mailu"                                                                                   |
| mailu_docker_user                   | User that will be used to run/won the mailu containers                     | root                                                                                       |
| mailu_docker_compose                | Path to mailu docker-compose template                                      | "{{ role_path }}/templates/docker-compose.yml.j2"                                          |
| mailu_docker_compose_env            | Path to mailu docker-compose env file                                      | "{{ role_path }}/templates/docker-compose.env.j2"                                          |
| mailu_version                       | Mailu version to use                                                       | 1.8                                                                                        |
| mailu_docker_subnet                 | Subnet used by docker-compose for mailu                                    | 172.18.0.0/16                                                                              |
| mailu_dns_ip                        | IP adres that will be used by the resolver container                       | 172.18.10.10                                                                               |
| mailu_initial_admin_username        | Name for initial account that will be created                              | admin (will result in username admin@{{ mailu_env_mail_domain }})                          |
| mailu_initial_admin_password        | Password for initial account that will be created                          | Aasnd3hn7dn3nf7wfnoj84                                                                     |
| mailu_env_file                      | Mailu env file                                                             | "{{ role_path }}/templates/`mailu.env.j2`"                                                 |
| mailu_env_api_token                 | Env file variable, see `mailu.env.j2` template for more info for more info | F1JqJeRr46hPcQZdgn0i                                                                       |
| mailu_env_secret_key                | Env file variable, see `mailu.env.j2` template for more info for more info | CUFJMQHXJJY84WVC                                                                           |
| mailu_env_mail_domain               | Env file variable, see `mailu.env.j2` template for more info for more info | example.net                                                                                |
| mailu_env_hostnames                 | Env file variable, see `mailu.env.j2` template for more info for more info | mailhost                                                                                   |
| mailu_env_postmaster                | Env file variable, see `mailu.env.j2` template for more info for more info | admin                                                                                      |
| mailu_env_tls_flavor                | Env file variable, see `mailu.env.j2` template for more info for more info | notls                                                                                      |
| mailu_env_auth_ratelimit            | Env file variable, see `mailu.env.j2` template for more info for more info | 10/minute;1000/hour                                                                        |
| mailu_env_opt_out_stats             | Env file variable, see `mailu.env.j2` template for more info for more info | "True"                                                                                     |
| mailu_env_admin_interface           | Env file variable, see `mailu.env.j2` template for more info for more info | "true"                                                                                     |
| mailu_env_webmail_product           | Env file variable, see `mailu.env.j2` template for more info for more info | snappymail                                                                                 |
| mailu_env_webdav_product            | Env file variable, see `mailu.env.j2` template for more info for more info | none                                                                                       |
| mailu_env_antivirus_product         | Env file variable, see `mailu.env.j2` template for more info for more info | none                                                                                       |
| mailu_env_message_size_limit        | Env file variable, see `mailu.env.j2` template for more info for more info | 50000000                                                                                   |
| mailu_env_relay_nets                | Env file variable, see `mailu.env.j2` template for more info for more info |                                                                                            |
| mailu_env_relay_host                | Env file variable, see `mailu.env.j2` template for more info for more info |                                                                                            |
| mailu_env_fetchmail_delay           | Env file variable, see `mailu.env.j2` template for more info for more info | 600                                                                                        |
| mailu_env_recipient_delimiter       | Env file variable, see `mailu.env.j2` template for more info for more info | +                                                                                          |
| mailu_env_dmarc_rua                 | Env file variable, see `mailu.env.j2` template for more info for more info | admin                                                                                      |
| mailu_env_dmarc_ruf                 | Env file variable, see `mailu.env.j2` template for more info for more info | admin                                                                                      |
| mailu_env_welcome                   | Env file variable, see `mailu.env.j2` template for more info for more info | "false"                                                                                    |
| mailu_env_welcome_subject           | Env file variable, see `mailu.env.j2` template for more info for more info | "Welcome to your new mail account"                                                         |
| mailu_env_welcome_body              | Env file variable, see `mailu.env.j2` template for more info for more info | "Welcome to your new email account, if you can read this, then it is configured properly!" |
| mailu_env_compression               | Env file variable, see `mailu.env.j2` template for more info for more info |                                                                                            |
| mailu_env_compression_level         | Env file variable, see `mailu.env.j2` template for more info for more info |                                                                                            |
| mailu_env_webroot_redirect          | Env file variable, see `mailu.env.j2` template for more info for more info | /webmail                                                                                   |
| mailu_env_web_admin_path            | Env file variable, see `mailu.env.j2` template for more info for more info | /admin                                                                                     |
| mailu_env_webmail_path              | Env file variable, see `mailu.env.j2` template for more info for more info | /webmail                                                                                   |
| mailu_env_api_path                  | Env file variable, see `mailu.env.j2` template for more info for more info | /api                                                                                       |
| mailu_env_sitename                  | Env file variable, see `mailu.env.j2` template for more info for more info | Mailu                                                                                      |
| mailu_env_website                   | Env file variable, see `mailu.env.j2` template for more info for more info | https://github.com/justin-p/                                                               |
| mailu_env_compose_project_name      | Env file variable, see `mailu.env.j2` template for more info for more info | mailu                                                                                      |
| mailu_env_password_scheme           | Env file variable, see `mailu.env.j2` template for more info for more info | BLF-CRYPT                                                                                  |
| mailu_env_real_ip_header            | Env file variable, see `mailu.env.j2` template for more info for more info |                                                                                            |
| mailu_env_real_ip_from              | Env file variable, see `mailu.env.j2` template for more info for more info |                                                                                            |
| mailu_env_reject_unlisted_recipient | Env file variable, see `mailu.env.j2` template for more info for more info |                                                                                            |
| mailu_env_log_level                 | Env file variable, see `mailu.env.j2` template for more info for more info | WARNING                                                                                    |
| mailu_env_tz                        | Env file variable, see `mailu.env.j2` template for more info for more info | Etc/UTC                                                                                    |
| mailu_env_default_spam_threshold    | Env file variable, see `mailu.env.j2` template for more info for more info | 80                                                                                         |

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

## Example Playbook

### Default role installation

```yaml
---
- hosts: mailu_hosts
  become: yes
  roles:
    - role: justin_p.mailu
```

### Deployment playbook

```yaml
---
- hosts: mailu_hosts
  become: yes
  tasks:
    - name: Run 'robertdebock.update_package_cache'-role
      ansible.builtin.include_role:
        name: robertdebock.update_package_cache

    - name: Run 'robertdebock.core_dependencies'-role
      ansible.builtin.include_role:
        name: robertdebock.core_dependencies

    - name: Run 'robertdebock.bootstrap'-role
      ansible.builtin.include_role:
        name: robertdebock.bootstrap

    - name: Run 'robertdebock.epel'-role
      ansible.builtin.include_role:
        name: robertdebock.epel

    - name: Run 'robertdebock.update'-role
      ansible.builtin.include_role:
        name: robertdebock.update
      vars:
        update_reboot: false

    - name: Run 'robertdebock.firewall'-role
      ansible.builtin.include_role:
        name: robertdebock.firewall
      vars:
        firewall_services:
          - name: ssh  #  and other rules for mailu, but you can figure that out yourself.

    - name: Run 'robertdebock.hostname'-role
      ansible.builtin.include_role:
        name: robertdebock.hostname
      vars:
        hostname: mailhost.domain.tld
        hostname_reboot: true

    - name: Flush handlers triggered turing bootstrap
      meta: flush_handlers

    - name: Install and harden docker
      include_role:
        name: justin_p.bootstrap_docker
      vars:
        bsd_docker_username: docker_user
        bsd_docker_password: StrongPassword01!
        bsd_docker_password_salt: SomeSaltsPlease
        bsd_docker_iptables_template: "{{ playbook_dir }}/templates/rules.v4.j2"

    - name: Flush handlers triggered turing bootstrap_docker
      meta: flush_handlers

    - name: Install mailu
      include_role:
        name: justin_p.mailu
      vars:
        mailu_docker_subnet: "{{ docker_subnet }}" # 172.18.0.0/16
        mailu_docker_user: docker_user
        mailu_install_path: /home/docker_user/mailu
        mailu_env_secret_key: 16_char_random_long_string
        mailu_env_hostnames: mailhost.domain.tld
        mailu_env_mail_domain: domain.tld
        mailu_initial_admin_password: StrongPassword01!
```

## License

MIT

## Authors

Justin Perdok ([@justin-p](https://github.com/justin-p/)), Orange Cyberdefense

## Contributing

Feel free to open issues, contribute and submit your Pull Requests. You can also ping me on Twitter ([@JustinPerdok](https://twitter.com/JustinPerdok))
