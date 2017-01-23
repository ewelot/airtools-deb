# airtools-deb
Debian package repository related to [AIRTOOLS](https://github.com/ewelot/airtools) (Astronomical Image Reduction TOOLSet)  

## Howto install packages from this repository
```
sudo apt-get install apt-transport-https  
sudo cat << EOF >> /etc/apt/sources.list  
deb https://raw.githubusercontent.com/ewelot/airtools-deb/jessie jessie main  
EOF  
sudo apt-get update  
sudo apt-get install airtools
```

