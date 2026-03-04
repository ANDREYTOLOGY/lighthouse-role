lighthouse-role
=========

Устанавливает LightHouse и настраивает nginx для раздачи статического интерфейса.

Requirements
------------

Debian/Ubuntu (APT), systemd.


Role Variables
--------------

- `lighthouse_repo` — репозиторий LightHouse
- `lighthouse_version` — ветка/тег/коммит (по умолчанию `master`)
- `lighthouse_root` — каталог размещения (по умолчанию `/var/www/lighthouse`)
- `lighthouse_server_name` — server_name в nginx (по умолчанию `_`)
- `lighthouse_listen_port` — порт nginx (по умолчанию `80`)
- `lighthouse_nginx_conf_path` — путь vhost-конфига nginx


Example Playbook
----------------

```YAML
- hosts: vector
  become: true
  roles:
    - role: vector
      vector_version: "0.34.1"
      vector_config_path: /etc/vector/vector.yaml

      vector_sources:
        demo_logs:
          type: demo_logs
          format: syslog

      vector_sinks:
        out:
          type: console
          inputs: ["demo_logs"]
          encoding:
            codec: json
```

License
-------

BSD

Author Information
------------------

Andrey Chernyshov
System Administrator  
GitHub: https://github.com/ANDREYTOLOGY
