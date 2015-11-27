Gogs for Yunohost
============

[Yunohost project](https://yunohost.org/#/)

A self-hosted Git service written in Go.

Official website: <http://gogs.io/>

Gogs v0.7.22

Arch:
Gogs will be build in the installation so it is compatible with all arch.

TODO
 - Backup and restore script
 
FOR DEVELOPPER : 

Please do your pull request to the dev branch.

sources files (sources/gogs_src.tar.gz) is build with this command :
```
mkdir -p /opt/gogs_src/src/github.com/gogits
cd /opt/gogs_src/src/github.com/gogits
git clone --depth=500 -b master https://github.com/gogits/gogs
cd gogs
git reset --hard v0.7.22    # adapt version
GOPATH=/opt/gogs_src: go get -d ./...
cd /opt/gogs_src
find . -name ".git" -type d -exec rm -rf {} \; # drastically reduced zip size
cd /opt
tar czf gogs_src.tar.gz gogs_src
```