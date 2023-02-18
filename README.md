# Ansible Role: Mailpit

Installs [Mailpit](https://github.com/axllent/mailpit), a Go-based SMTP server and web UI/API for displaying captured emails, on RedHat or Debian-based linux systems.

If you're using PHP and would like to route all PHP email into Mailpit, you will need to update the `sendmail_path` configuration option in php.ini, like so:

    sendmail_path = "{{ mailpit_install_dir }}/mailpit sendmail"

(Replace `{{ mailpit_install_dir }}` with the actual Mailpit installation directory, which is `/opt/mailpit` by default.

This role is based on https://github.com/geerlingguy/ansible-role-mailhog

## Requirements

* systemd

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    mailpit_install_dir: /opt/mailpit

The directory into which the MailHog binary will be installed.

    mailpit_version: 1.0.0

The version of Mailpit that will be installed. You can find the latest version by visiting the [Mailpit project releases page](https://github.com/axllent/mailpit/releases).

    mailpit_release_url: "https://github.com/axllent/mailpit/releases/download/v{{ mailpit_version }}/mailhog-linux-amd64"

The Mailpit binary that will be installed. You can find the latest version by visiting the [MailHog project releases page](https://github.com/mailpit/MailHog/releases).

    mailpit_daemonize_bin_path: /usr/sbin/daemonize

The path to `daemonize`, which is used to launch MailHog via init script.

    mhsendmail_version: 0.2.0

## Dependencies

  - geerlingguy.daemonize

## Example Playbook

    - hosts: servers
      roles:
        - { role: roots.mailpit }
