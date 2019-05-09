# ethercat

$sudo apt-get install mercurial

$hg clone http://hg.code.sf.net/p/etherlabmaster/code ethercat-hg

$cd ethercat-hg

$./bootstrap

$./configure --prefix=/home/user/WorkArea/app/ethercat-hg/output --with-linux-dir=/home/user/WorkArea/buildroot_som1/linux-at91 --enable-8139too=no --enable-generic=yes CC=arm-linux-gnueabihf-gcc --host=arm-none-linux-gnueabihf

$make -j8

# TODO...
# make modules


