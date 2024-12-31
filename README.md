# Ansible Role: docker_engine

An Ansible role that deploys [Docker][01] on Linux boxes.

## 🚀 Motivation

Installing docker manually on several hosts can be tedious. It would be nice to automate this task.

## 📑 Role Variables

Check [here][02].

## 🧰 Dependencies

None.

## ⚡ Quick start

An example of how integrate this role to an Ansible playbook can be found here:

```yml
---
- name: Deploy docker
  hosts: all
  become: true
  gather_facts: true
  roles:
    - fernandobohrer.docker_engine
```

If you want to add the `johndoe` user do the `docker` group, just add the user to the `docker_engine__users` variable:

```yml
---
- name: Deploy docker
  hosts: all
  become: true
  gather_facts: true
  vars:
    docker_engine__users:
      - johndoe
  roles:
    - fernandobohrer.docker_engine
```

## ⚙️ Compatibility

This role was tested on and is confirmed to work with the following Linux distributions:

- `Debian 12`
- `Ubuntu 22.04`
- `Ubuntu 24.04`

Details can be found in the [Molecule][03] scenarios available in the `molecule` folder.

## ⚠️ Warning

This Ansible role was tested on the above mentioned Linux distributions considering their default configuration. Your environment might have a different configuration or requirements which might conflict with the options that this role uses.

With the above in mind, it is **imperative** that you familiarize yourself with what this role does and test it on non-production machines **before** applying it to machines in a production environment.

## 📝 License

This project is licensed under the terms of the [MIT license][04].

[01]: https://docs.docker.com/engine/
[02]: defaults/main.yml
[03]: https://github.com/fernandobohrer/ansible-molecule-scenarios
[04]: /LICENSE
