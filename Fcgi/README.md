#!/bin/sh
# \file         Fcgi/README.md
# \author       Bill Hill
# \date         February 2016
# \version      $Id$
#
# To build the FCGI library for the Woolz IIP server follow the
# steps below or copy edit and run this script.

# setenv MA ~/MouseAtlas/Build/
#export MA=~/MouseAtlas/Build/
export MA=/opt/MouseAtlas/
# set path = ("$MA"/bin $path)
export PATH="$MA"/bin:$PATH
# setenv LD_LIBRARY_PATH "$MA"/lib:$LD_LIBRARY_PATH
export LD_LIBRARY_PATH="$MA"/lib:$LD_LIBRARY_PATH

# Cleanup
#rm -rf 

# Unpack archive and patch
tar -zxf fcgi-2.4.0.tar.gz
patch -p0 < fcgi-2.4.0-patch-01

# Configure for use with Woolz
cd fcgi-2.4.0
./configure --prefix=$MA --enable-static --disable-shared

make
make install
cd ..

# Cleanup
# rm -rf fcgi-2.4.0
