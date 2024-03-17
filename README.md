# debian-onefetch

## Misc
- help2man onefetch -n "Command-line Git information tool" >docs/onefetch.1

## Deploy to launchpad
- wget https://github.com/o2sh/onefetch/archive/2.18.1.tar.gz
- tar xzvf 2.18.1.tar.gz
- cd onefetch-2.18.1/ && rm -f Makefile
- cargo vendor debian/vendor
- cd debian && tar zcf vendor.tar.gz vendor && rm -Rf vendor
- cp -R ~/dev/debian-onefetch/debian/* .
- update changelog and files
- cd ..
- dpkg-buildpackage -S -us -uc
- cd ..
- debsign onefetch_2.9.0-1_source.changes
- dput -f ppa:o2sh/onefetch onefetch_2.9.0-1_source.changes

## Build standalone debian package
- dpkg-buildpackage -rfakeroot
