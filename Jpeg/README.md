#!/bin/sh
# \file         Jpeg/README.md
# \author       Bill Hill
# \date         January 2012
# \version      $Id$
#
# To build the Jpeg libraries for the Woolz applications follow the
# steps below or copy edit and run this script.

set -x

# setenv MA ~/MouseAtlas/Build/
#export MA=~/MouseAtlas/Build/
export MA=/opt/MouseAtlas/
# set path = ("$MA"/bin $path)
export PATH="$MA"/bin:$PATH
# setenv LD_LIBRARY_PATH "$MA"/lib:$LD_LIBRARY_PATH
export LD_LIBRARY_PATH="$MA"/lib:$LD_LIBRARY_PATH

# Cleanup
rm -rf libjpeg-turbo-1.5.1

# Unpack archive
tar -zxf libjpeg-turbo-1.5.1.tar.gz

# Configure for use with Woolz
cd libjpeg-turbo-1.5.1
autoreconf -fi
./configure --prefix $MA \
            --disable-shared \
	    --enable-static \
	    --with-jpeg7 \
	    --with-pic

make
make install
cd ..

# Cleanup
# rm -rf libjpeg-turbo-1.5.1
