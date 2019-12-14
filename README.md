# Ansible Role: NFS

[![Build Status](https://travis-ci.org/richardskumat/ansible-role-nfs.svg?branch=master)](https://travis-ci.org/richardskumat/ansible-role-nfs)

Installs NFS utilities on RedHat/CentOS or Debian/Ubuntu.

This is a personal fork of [geerlingguy/ansible-role-nfs](https://github.com/richardskumat/ansible-role-nfs).

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    nfs_exports: []

A list of exports which will be placed in the `/etc/exports` file. See Ubuntu's simple [Network File System (NFS)](https://help.ubuntu.com/lts/serverguide/network-file-system.html.en) guide for more info and examples. (Simple example: `nfs_exports: [ "/home/public    *(rw,sync,no_root_squash)" ]`).

    nfs_rpcbind_state: started
    nfs_rpcbind_enabled: true

(RedHat/CentOS/Fedora only) The state of the `rpcbind` service, and whether it should be enabled at system boot.

    RPCMOUNTDOPTS_OPTIONS: '"--manage-gids"'

Options for rpc.mountd for a templating task for Debian based distros.

Added so that a static port can be set for rpc.mountd.


## Dependencies

None.

## Example Playbook

    - hosts: db-servers
      roles:
        - { role: geerlingguy.nfs }

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
