# ethercat

$sudo apt-get install mercurial

$hg clone http://hg.code.sf.net/p/etherlabmaster/code ethercat-hg

$cd ethercat-hg

$./bootstrap

$./configure --prefix=/home/user/WorkArea/app/ethercat-hg/output --with-linux-dir=/home/user/WorkArea/buildroot_som1/linux-at91 --enable-8139too=no --enable-generic=yes CC=arm-linux-gnueabihf-gcc --host=arm-none-linux-gnueabihf

$make -j8

$make install

# make modules
$make ARCH-arm CROSS_COMPILE=arm-none-linux-gnueabihf- modules

$mkdir output/modules

$cp devices/ec_generic.ko output/modules

$cp master/ec_master.ko output/modules

tar -cjf output.tar.bz2 output

# TODO...

#in target board
copy all files from output folder to its position

$cp ec_master.ko /lib/mkdules/xxxx/
$depmod



# Ethercat test
$/etc/init.d/ethercat start

$insmod output/modules/ec_generic.ko

$ethercat pdos

