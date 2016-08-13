# nx9-on-linux
some hacky stuff to make Siemens NX9 CAD run on debian and use the license server via SSH tunnel


NX9 unter Linux:




Making the installer work:
```
apt-get install ksh libxp6 openjdk-7-jre
dpkg --add-architecture i386
apt-get update
apt-get install libc6-i386
ln -s /tmp /usr/tmp
export LC_NUMERIC=C
# otherwise arithmetic error in:  UG_VER=V"$(($NX_VER + 18))" 
```

patch the installer (TODO document this) and run it. It needs to be run as root because it sets some environment stuff.




Starting NX:
```
export UGII_ROOT_DIR=/home/max/install/nx/install_ugs090/bin/
export UGII_BASE_DIR=/home/max/install/nx/install_ugs090/
cd $UGII_ROOT_DIR
./ugspawn
```


Starting with license server via SSH tunnel:
use the script provided here, copy config.example to config and adapt to your needs
