# \file         cJSON/README.md
# \author       Bill Hill
# \date         April 2021
# \version      $Id$
#
# To build a cJSON library for the Woolz applications follow the
# steps below or copy edit and run this script.
# cJSON was downloaded as a release from https://github.com/DaveGamble/cJSON

# setenv MA ~/MouseAtlas/Build/
#export MA=~/MouseAtlas/Build/
export MA=/opt/MouseAtlas/
# set path = ("$MA"/bin $path)
export PATH="$MA"/bin:$PATH
# setenv LD_LIBRARY_PATH "$MA"/lib:$LD_LIBRARY_PATH
export LD_LIBRARY_PATH="$MA"/lib:$LD_LIBRARY_PATH

# Cleanup
#rm -rf cJSON-1.7.14

# Unpack archive
#tar -zxf cJSON-1.7.14.tar.gz

# Configure for use with Woolz
mkdir cJSON-1.7.14-build
cd cJSON-1.7.14-build
cmake -DENABLE_CJSON_TEST=Off -DBUILD_SHARED_AND_STATIC_LIBS=On \
      -DCMAKE_INSTALL_PREFIX=$MA ../cJSON-1.7.14

# Build
make

# Install
cp libcjson.a $MA/lib/
cp cJSON.h $MA/include/

# Cleanup
cd ..
rm -f cJSON-1.7.14  cJSON-1.7.14-build
