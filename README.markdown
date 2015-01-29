Gogs for Yunohost
============

[Yunohost project](https://yunohost.org/#/)

A self-hosted Git service written in Go.

Official website: <http://gogs.io/>

Gogs v0.5.11

Work:
 - The app :D
 - SSO with the first user

Don't work for now:
 - Not fully automated, still have to populate an admin (same name as your yunohost user) and click install
 - LDAP (not configured)

TODO
 - finish install with curl and admin / password / email
 - ldap config in database
 - find a way to don't use app password but ldap auth for the admin
 - upgrade script