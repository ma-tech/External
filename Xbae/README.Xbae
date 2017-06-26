#!/bin/sh
# \file         README.Xbae
# \author       Bill Hill
# \date         January 2012
# \version      $Id$
#
# To build the Xbae libraries for the Woolz applications follow the
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
rm -rf xbae-4.60.4

# Unpack archive
tar -zxf xbae-4.60.4.tar.gz

# Configure for use with Woolz
cd xbae-4.60.4
./configure --prefix $MA \
            --disable-shared \
	    --enable-static \
	    --with-pic

make
make install
cd ..

# Cleanup
# rm -rf xbae-4.60.4
