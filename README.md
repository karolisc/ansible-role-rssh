# ansible-role-rssh

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-rssh.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-rssh)

RHEL/CentOS - Restricted shell for scp/sftp

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    rssh_allowcvs: False
    rssh_allowrdist: False
    rssh_allowrsync: False
    rssh_allowscp: False
    rssh_allowsftp: False
    rssh_logfacility: LOG_USER
    rssh_umask: '022'

Additional variables available, not set by default:

    rssh_chrootpath: /usr/local/chroot
    rssh_users:
      tkimball:
        umask: '022'
        access_bits: '00001'
        path: /usr/local/chroot

## Dependencies

 * https://galaxy.ansible.com/linuxhq/epel/

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.rssh
          rssh_chrootpath: /usr/local/chroot

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
