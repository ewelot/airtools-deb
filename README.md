# airtools-deb
Debian package repository related to [AIRTOOLS](https://github.com/ewelot/airtools)
(Astronomical Image Reduction TOOLSet)  

The repository contains 64bit binary packages for the following Linux distributions:  
  - Debian 8 "Jessie"  
  - Ubuntu 16.04 "Xenial" (and variants like XUbuntu)


## Howto install packages from this repository

Open a terminal window.

Create temporary script file /tmp/script.sh (copy and paste the following code
block into the terminal window):
```
cat <<EOF > /tmp/script.sh
#!/bin/bash
# determine codename of your distribution
dist=\$(lsb_release -s -c)
# download packages
repo=airtools-deb
url=https://github.com/ewelot/\$repo.git/trunk/\$dist
ddir=/usr/local/share/\$repo
test ! -d \$ddir && mkdir -p \$ddir
apt-get update
apt-get -y install subversion apt-utils
(cd \$ddir && svn export \$url/main)
# add local package repository
echo "deb file://\$ddir/\$dist main/" > /etc/apt/sources.list.d/airtools.list
apt-get update  
EOF
```

Get local copy of package repository by executing the script:
```
sudo bash /tmp/script.sh
```

Install airtools and all dependent software:
```
sudo apt-get -y --allow-unauthenticated install airtools
```
