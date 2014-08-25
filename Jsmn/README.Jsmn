#!/bin/sh
# \file         README.Jsmn
# \author       Bill Hill
# \date         October 2013
# \version      $Id$
#
# To build the Jsmn library for applications follow the
# steps below or copy edit and run this script.

set -x

# setenv MA ~/MouseAtlas/Build/
#export MA=~/MouseAtlas/Build/
export MA=/opt/MouseAtlas/

# Cleanup
rm -rf jsmn

# Unpack archive
tar -zxf jsmn-20131022.tgz

# Make and install
cd jsmn
make
cp jsmn.h $MA/include/
cp libjsmn.a $MA/lib
cd ..

# Cleanup
# rm -rf jsmn
