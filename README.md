# airtools-deb
Debian package repository related to [AIRTOOLS](https://github.com/ewelot/airtools) (Astronomical Image Reduction TOOLSet)  

The repository contains 64bit binary packages for the following Linux distributions:  
  - Debian 8 "Jessie"  
  - Ubuntu 16.04 "Xenial" (and variants like XUbuntu)


## Howto install packages from this repository
```
# determine codename of your distribution
dist=$(lsb_release -s -c)
# add package repository
url=https://raw.githubusercontent.com/ewelot/airtools-deb
echo "deb $url/$dist $dist main" | sudo tee -a /etc/apt/sources.list
sudo apt-get install apt-transport-https
sudo apt-get update  
# install airtools and all dependent software
sudo apt-get install airtools
```

