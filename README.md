# [Ansible role eclipse](#ansible-role-eclipse)

Install eclipse and plugins on your system.

|GitHub|GitLab|Downloads|Version|
|------|------|---------|-------|
|[![github](https://github.com/buluma/ansible-role-eclipse/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-eclipse/actions)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-eclipse/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-eclipse)|[![downloads](https://img.shields.io/ansible/role/d/buluma/eclipse)](https://galaxy.ansible.com/buluma/eclipse)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-eclipse.svg)](https://github.com/buluma/ansible-role-eclipse/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-eclipse/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
  - become: true
    gather_facts: true
    hosts: all
    name: Converge
    roles:
      - eclipse_install_path: /opt/eclipse-{{ eclipse_release }}
        eclipse_release: 2024‑06
        role: buluma.eclipse
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-eclipse/blob/master/molecule/default/prepare.yml):

```yaml
---
  - become: true
    gather_facts: false
    hosts: all
    name: Prepare
    roles:
      - role: buluma.bootstrap
      - role: buluma.core_dependencies
      - role: buluma.java
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-eclipse/blob/master/defaults/main.yml):

```yaml
---
eclipse_archive_mirror: 
  http://ftp.snt.utwente.nl/pub/software/eclipse/technology/epp/downloads/release
eclipse_install_lombok: true
eclipse_install_maven: true
eclipse_install_path: /opt/eclipse-{{ eclipse_release }}
eclipse_link_paths:
  - /opt/eclipse
eclipse_lombok_version: 1.18.34
eclipse_plugins: []
eclipse_release: 2024-06
eclipse_release_type: java
eclipse_release_version: R
eclipse_tmp_path: /tmp
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-eclipse/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.core_dependencies](https://galaxy.ansible.com/buluma/core_dependencies)|[![Build Status GitHub](https://github.com/buluma/ansible-role-core_dependencies/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-core_dependencies/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-core_dependencies/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-core_dependencies)|
|[buluma.java](https://galaxy.ansible.com/buluma/java)|[![Build Status GitHub](https://github.com/buluma/ansible-role-java/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-java/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-java/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-java)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-eclipse/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Amazon](https://hub.docker.com/r/buluma/amazonlinux)|all|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|all|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[opensuse](https://hub.docker.com/r/buluma/opensuse)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-eclipse/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-eclipse/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

