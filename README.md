# Ansible Role: Drush

Installs Drush, a command line shell and scripting interface for Drupal, on any Linux or UNIX system.

This fork of original geerlingguy's repository does not depend on any external playbooks so it's assumed you already have PHP, Composer and Git installed.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    drush_install_path: /usr/local/share/drush

The location of the entire drush installation (includes all the supporting files, as well as the `drush` executable file.

    drush_path: /usr/local/bin/drush

The path where composer will be installed and available to your system. Should be in your user's `$PATH` so you can run commands simply with `composer` instead of the full path.

This role also relies on the presence of the `composer_path` variable, which is used to run composer. This could be, simply, `composer` on your system (if composer is in your user's `$PATH`).

    drush_version: master

The version of Drush to install (examples: `master` for the bleeding edge, `7.x`, `6.x`, `6.2.0`).

    drush_keep_updated: no

Whether to keep Drush up-to-date with the latest revision of the branch specified by `drush_version`.

## Example Playbook

    - hosts: servers
      roles:
        - { role: geerlingguy.drush }

After the playbook runs, the `drush` command will be accessible from normal system accounts.

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
