# Ansible Role for YUM Repos

An Ansible Role for managing YUM repos

## Variables

Here is an example variables file

```
repositories_manage_all: false # Don't remove all other repos
repositories:
  edr:
    base:
      name: "{{ ansible_distribution }}{{ ansible_distribution_major_version }} - Base"
      baseurl: "http://<URL>/mirror/{{ ansible_distribution|lower }}/{{ ansible_distribution_major_version }}/os/{{ ansible_architecture }}/"
      gpgcheck: 0
```

## Example Task with role

```
- name: manage repos
  hosts: all
  roles:
    - edr.repos
```
