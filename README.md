# Ansible Role: Mailpit

<a href="https://github.com/roots/ansible-role-mailpit/releases"><img alt="Release" src="https://img.shields.io/github/release/roots/ansible-role-mailpit.svg?style=flat-square" /></a>
<a href="https://github.com/roots/ansible-role-mailpit/actions"><img alt="Build Status" src="https://img.shields.io/github/actions/workflow/status/roots/ansible-role-mailpit/ci.yml?branch=main&style=flat-square" /></a>
<a href="https://galaxy.ansible.com/roots/mailpit"><img alt="Galaxy Downloads" src="https://img.shields.io/badge/dynamic/json?color=blueviolet&label=galaxy%20downloads&query=%24.download_count&url=https%3A%2F%2Fgalaxy.ansible.com%2Fapi%2Fv1%2Froles%2F24936%2F%3Fformat%3Djson&style=flat-square" /></a>
<a href="https://twitter.com/rootswp"><img alt="Follow Roots" src="https://img.shields.io/badge/follow%20@rootswp-1da1f2?logo=twitter&logoColor=ffffff&message=&style=flat-square"></a>
<a href="https://github.com/sponsors/roots"><img src="https://img.shields.io/badge/sponsor%20roots-525ddc?logo=github&style=flat-square&logoColor=ffffff&message=" alt="Sponsor Roots"></a>

Installs [Mailpit](https://github.com/axllent/mailpit), an email testing tool for developers, on RedHat or Debian-based linux systems.
Mailpit acts as both an SMTP server, and provides a web interface to view all captured emails. Mailpit is inspired by MailHog, but much, much faster.

This role is based on https://github.com/geerlingguy/ansible-role-mailhog

If you're using PHP and would like to route all PHP email into Mailpit, you will need to update the `sendmail_path` configuration option in php.ini, like so:

```yaml
sendmail_path = "{{ mailpit_install_dir }}/mailpit sendmail"
```

## Support us

Roots is an independent open source org, supported only by developers like you. Your sponsorship funds [WP Packages](https://wp-packages.org/) and the entire Roots ecosystem, and keeps them independent. Support us by purchasing [Radicle](https://roots.io/radicle/) or [sponsoring us on GitHub](https://github.com/sponsors/roots) — sponsors get access to our private Discord.

## Requirements

A Debian-based (eg: Ubuntu) or RedHat system running systemd.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
mailpit_install_dir: /opt/mailpit
```

The directory into which the MailHog binary will be installed.

```yaml
mailpit_version: 1.3.8
```

The version of Mailpit that will be installed. You can find the latest version by visiting the [Mailpit project releases page](https://github.com/axllent/mailpit/releases).

```yaml
mailpit_release_url: "https://github.com/axllent/mailpit/releases/download/v{{ mailpit_version }}/mailhog-linux-amd64"
```

## Example Playbook

```yaml
- hosts: servers
  roles:
    - { role: roots.mailpit }
```

## Community

Keep track of development and community news.

- Join us on Discord by [sponsoring us on GitHub](https://github.com/sponsors/roots)
- Join us on [Roots Discourse](https://discourse.roots.io/)
- Follow [@rootswp on Twitter](https://twitter.com/rootswp)
- Follow the [Roots Blog](https://roots.io/blog/)
- Subscribe to the [Roots Newsletter](https://roots.io/subscribe/)
