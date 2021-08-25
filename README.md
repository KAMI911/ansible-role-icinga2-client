# Ansible Role: Installs Icinga 2 client

Icinga 2 client installation on Linux.

Travis status:   [![Build Status](https://travis-ci.org/KAMI911/ansible-role-icinga2-client.svg?branch=master)](https://travis-ci.org/KAMI911/ansible-role-icinga2-client)
Code Climate status: [![Code Climate](https://codeclimate.com/github/KAMI911/ansible-role-icinga2-client/badges/gpa.svg)](https://codeclimate.com/github/KAMI911/ansible-role-icinga2-client)
Test Coverage status: [![Test Coverage](https://codeclimate.com/github/KAMI911/ansible-role-icinga2-client/badges/coverage.svg)](https://codeclimate.com/github/KAMI911/ansible-role-icinga2-client/coverage)

## Table of Contents

1. [Requirements][Requirements]
2. [Installation][Installation]
3. [Role Variables][Role Variables]
4. [Dependencies][Dependencies]
5. [Example Playbook][Example Playbook]
6. [Licensing][Licensing]
7. [Author Information][Author Information]
8. [Support][Support]
9. [Contributing][Contributing]
10. [Donation][Donation]

## Requirements

None.

## Installation

    ansible-galaxy install kami911.icinga2-client

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    icinga2_server: icinga.server.org

Specify of your Icinga 2 master installation's FQDN address.

    icinga2_server_port: 5665

Icinga 2 port to use. (You don't want to change it in default installations.)

    icinga2_ticket_salt: q08TgeMcBv03ViwQB04dcJqEgnT5CVZC

Ticket salt. Please change it for your configuration.

    icinga2_server_user: icinga

Icinga 2 client local user.

    icinga2_server_group: icinga

Icinga 2 client local group.

    icinga2_add_repository: true

Add Official Icinga 2 repository to the system. False means Icinga 2 packages are already on your system or installable via package manager.

    icinga2_disable_confd: false

Disable recurse inclusion of conf.d in Icinga 2 configuration. Add the ability to disable the conf.d inclusion through running node wizard. Inclusion can cause some strange behavior.

    icinga2_do_replace_confd: false

Enable replace of confd string.

    icinga2_replace_confd: "conf.d/commands"

Include only new commands, not any host specific other things that can cause strange behaviors.

    icinga2_pki_path: '/var/lib/icinga2/certs/'

Configure Icinga PKI folder. The default location was changed in Icinga 2 2.8 version. The current default is: /var/lib/icinga2/certs/ and the old default was: /etc/icinga2/pki/

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
        - icinga2-client

## Licensing

The lactransformer application and documantations are licensed under the terms of
the MIT / BSD, you will find a copy of this license in the
[LICENSE](LICENSE) file included in the source package.

## Author Information

This role was created in 2016-2018 by Kálmán Szalai - KAMI based on works of
Mark Mercado <mamercad@umflint.edu>

## Support

If you have any question, do not hesitate and drop me a line.
If you found a bug, or have a feature request, you can [fill an issue](https://github.com/KAMI911/ansible-role-icinga2-client/issues).

### Using as a submudule of an AWX playbook

#### Add as a submodule

```
git submodule add --force git@github.com:KAMI911/ansible-role-icinga2-client.git roles/icinga2-client
```

#### Update as sumodule

Update only this submodule

```
git submodule update --remote roles/icinga2-client/
```

Update all submodules:

```
git submodule foreach git pull origin master
```

## Contributing

There are many ways to contribute to ansible-role-icinga2-client -- whether it be sending patches,
testing, reporting bugs, or reviewing and updating the documentation. Every
contribution is appreciated!

Please continue reading in the [contributing chapter](CONTRIBUTING.md).

### Fork me on Github

SSH:

    git@github.com:KAMI911/ansible-role-icinga2-client.git

HTTPS:

    https://github.com/KAMI911/ansible-role-icinga2-client

Add a new remote `upstream` with this repository as value.

```
git remote add upstream https://github.com/KAMI911/ansible-role-icinga2-client.git
```

You can pull updates to your fork's master branch:

```
git fetch --all
git pull upstream HEAD
```

## Donation

If you find this useful, please consider a donation:

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=RLQZ58B26XSLA)

<!-- TOC URLs -->
[Requirements]: #requirements
[Installation]: #installation
[Role Variables]: #role_variables
[Dependencies]: #dependencies
[Example Playbook]: #example_playbook
[Licensing]: #licensing
[Author Information]: #author_information
[Support]: #support
[Contributing]: #contributing
[Donation]: #donation
