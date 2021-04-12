#!/bin/sh
# \file         PNG/README.md
# \author       Bill Hill
# \date         September 2013
# \version      $Id$
#
# To build the PNG libraries for the Woolz applications follow the
# steps below or copy edit and run this script.

# setenv MA ~/MouseAtlas/Build/
export MA=~/MouseAtlas/Build/
#export MA=/opt/MouseAtlas/
# set path = ("$MA"/bin $path)
export PATH="$MA"/bin:$PATH
# setenv LD_LIBRARY_PATH "$MA"/lib:$LD_LIBRARY_PATH
export LD_LIBRARY_PATH="$MA"/lib:$LD_LIBRARY_PATH

# Cleanup
rm -rf libpng-1.6.29

# Unpack archive
tar -zxf libpng-1.6.29.tar.gz

# Configure for use with Woolz
cd libpng-1.6.29
./configure --prefix $MA \
            --disable-shared \
	    --enable-static \
	    --with-pic

make
make install
cd ..

# Cleanup
# rm -rf libpng-1.6.29

