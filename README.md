[![Test deployment](https://github.com/GeekOops/geekoops-letsencrypt-apache/actions/workflows/CI.yml/badge.svg)](https://github.com/GeekOops/geekoops-letsencrypt-apache/actions/workflows/CI.yml)

# Letsencrypt SSL certificates using the apache webserver

Configurable ansible role for obtaining SSL certificates using an apache webserver. Works with

- openSUSE Leap 15.4 -> tested

Note: Apache should be already installed!

## Role Variables
--------------

You can set the following variables to configure the role. Here listed are the variables and their default settings.


| Value | Description | Default |
|-------|-------------|---------|
|`letsencrypt_domains` | domains to obtain certs for | "" |
|`letsencrypt_mail_address` | Who gets update notifications | "" |

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: jellyfish
      roles:
         - { role: geekoops-letsencrypt-apache, letsencrypt_domains: "www.example.org", letsencrypt_mail_address: "webmaster@example.org" }

An advanced example for the imaginary `jellyfish` test server

    - hosts: jellyfish
      roles:
         - role: geekoops-letsencrypt-apache
           vars:
             letsencrypt_mail_address: "webmaster@example.org"
             letsencrypt_domains:
               - "www.example.org"
               - "smtp.example.org"
               - "imap.example.org"

## License

MIT

# Development
- It would be nice to switch between nginx and apache
- Test on 15.3
