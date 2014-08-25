#!/bin/sh
# \file         README.MongoC
# \author       Bill Hill
# \date         October 2013
# \version      $Id$
#
# To build the MongoDB C driver library for the applications follow the
# steps below or copy edit and run this script.

set -x

# setenv MA ~/MouseAtlas/Build/
export MA=~/MouseAtlas/Build/debug
#export MA=/opt/MouseAtlas/

# Cleanup
rm -rf mongo-c-driver-0.8.1

# Unpack archive
tar -zxf mongo-c-driver-0.8.1.tgz

# Make and install
cd mongo-c-driver-0.8.1
make PREFIX=$MA
make PREFIX=$MA install
cd ..

# Cleanup
# rm -rf mongo-c-driver-0.8.1
