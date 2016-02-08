Gogs for Yunohost
=================

Gogs is a self-hosted Git service written in Go. Alternative to Github.
Official website: <http://gogs.io/>

Requirements
------------

Functionnal instance of [Yunohost](https://yunohost.org/#/)

Installation
------------

From command line:

`sudo yunohost app install -l Gogs https://github.com/mbugeia/gogs_ynh`

Upgrade
-------
From command line:

`sudo yunohost app upgrade -u https://github.com/mbugeia/gogs_ynh gogs`

Infos
-----
Gogs v0.8.10

Yunohost forum thread: https://forum.yunohost.org/t/gogs-package-an-awesome-github-alternative/1127

Architecture: Gogs will be build in the installation so it is compatible with all arch.

Debian compatibility: only Jessie is supported. 
It will install golang package from backport since Gogs need go >= 1.4 to build.

License
-------

Gogs is published under MIT License
https://github.com/gogits/gogs/blob/master/LICENSE

This package is published under MIT License

TODO
----
 - Backup and restore script need rework
 
Developper infos
----------------

Please do your pull request to the dev branch.

sources files (sources/gogs_src.tar.gz) is build with this command:
```
mkdir -p /opt/gogs_src/src/github.com/gogits
cd /opt/gogs_src/src/github.com/gogits
git clone --depth=500 -b master https://github.com/gogits/gogs
cd gogs
git reset --hard v0.8.10    # adapt version
GOPATH=/opt/gogs_src: go get -d ./...
cd /opt/gogs_src
find . -name ".git" -type d -exec rm -rf {} \; # drastically reduced zip size
cd /opt
tar czf gogs_src.tar.gz gogs_src
```

Test or upgrade to dev version:
```
su - admin
git clone -b dev https://github.com/mbugeia/gogs_ynh
# to install
sudo yunohost app install -l Gogs /home/admin/gogs_ynh
# to upgrade
sudo yunohost app upgrade -f /home/admin/gogs_ynh gogs

```