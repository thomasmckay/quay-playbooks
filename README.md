# quay-playbooks

## Local deployment

### Setup for local deployment

The [local-setup.yaml](role/local-setup.yaml) role will creaet all config folders, create TLS certs, and restart _docker.service_ after local installation of _rootCA.crt_.

```
ansible-playbook "$@" /dev/stdin <<EOF
- hosts: localhost
  tasks:
    - include: `pwd`/roles/local-setup.yaml
EOF
```

### Tear down local deployment

The [local-teardown.yaml](role/local-teardown.yaml) role will stop all containers and delete all config folders.

```
ansible-playbook "$@" /dev/stdin <<EOF
- hosts: localhost
  tasks:
    - include: `pwd`/roles/local-teardown.yaml
EOF
```

### Startup services

The [local-redis.yaml](role/local-redis.yaml) and [local-redis.yaml](role/local-redis.yaml) roles will start _redis_ and _postgresql_ containers with local storage.

```
ansible-playbook "$@" /dev/stdin <<EOF
- hosts: localhost
  tasks:
    - include: `pwd`/roles/local-redis.yaml
    - include: `pwd`/roles/local-postgresql.yaml
EOF
```

### Startup Quay

The [local-redis.yaml](role/local-redis.yaml) and [local-redis.yaml](role/local-redis.yaml) roles will start _redis_ and _postgresql_ containers with local storage.

```
ansible-playbook "$@" /dev/stdin <<EOF
- hosts: localhost
  vars:
    quay_image: quay.io/redhat/quay:v3.0.2
  tasks:
    - include: `pwd`/roles/local-quay.yaml
EOF
```

## Local deployment of Quay 2.9

### Run Quay 2.9

```
ansible-playbook "$@" /dev/stdin <<EOF
- hosts: localhost
  tasks:
    - include: `pwd`/roles/local-quay-2.9.yaml
EOF
```

### Backup Quay 2.9

```
ansible-playbook "$@" /dev/stdin <<EOF
- hosts: localhost
  tasks:
    - include: `pwd`/roles/local-quay-2.9-backup.yaml
EOF
```
