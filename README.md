# onefetch

- wget https://github.com/o2sh/onefetch/archive/2.18.1.tar.gz
- tar xzvf 2.18.1.tar.gz
- cp 2.18.1.tar.gz onefetch_2.18.1.orig.tar.gz
- cd onefetch-2.18.1/ && rm -f Makefile
- cargo vendor debian/vendor
- cd debian && tar zcf vendor.tar.gz vendor && rm -Rf vendor && cd ..
- update changelog and files
- cd ..
- dpkg-buildpackage -rfakeroot
- cd ..
- make sure you have the .dput.cf file in root folder
- dput mentors onefetch_2.18.1-1_amd64.changes
