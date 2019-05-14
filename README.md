# ansible-role-rssh

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-rssh.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-rssh)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-rssh-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/rssh)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

Linux - Restricted shell for scp/sftp

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    rssh_allowcvs: false
    rssh_allowrdist: false
    rssh_allowrsync: false
    rssh_allowscp: false
    rssh_allowsftp: false
    rssh_logfacility: LOG_USER
    rssh_umask: '022'
    rssh_users: []

Additional variables not defined by default:

    rssh_chrootpath: /usr/local/chroot

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.rssh
          rssh_allowrsync: true
          rssh_allowscp: true
          rssh_chrootpath: /usr/local/chroot
          rssh_users:
            - name: tkimball
              access_bits: '00001'
              path: /usr/local/chroot
              umask: '022'

``access_bits`` -  Five binary digits, which indicate whether the user is allowed to use rsync, rdist, cvs, sftp, and scp, in that order. One means the command is allowed, zero means it is not.

## License

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
