# fail2ban-cloudflare

This is a modification of a Cloudflare fail2ban action I found.

Since Cloudflare now supports multi-user setups, there may be the case where you need to allow another system administrator to control your Cloudflare zones without giving them the API key of the master account. This script supports such a use case.

## Prerequisites

* fail2ban -- 0.10.x is recommended, as older versions do not support IPv6.
* Your [Cloudflare API key](https://www.cloudflare.com/a/account/my-account) and Zone ID.

## Installation

1. Copy cloudflare-v4.conf into `/etc/fail2ban/actions.d`
2. Edit the values in the `[Init]` section of the file.
3. Edit your jail to use `cloudflare-v4` as an action.
4. Reload fail2ban (systemd: `systemctl reload fail2ban.service`)
