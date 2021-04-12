# \file         NIfTI/README.md
# \author       Bill Hill
# \date         April 2021
# \version      $Id$
#
# To build a NIfTI c library for the Woolz applications follow the
# steps below or copy edit and run this script.

# setenv MA ~/MouseAtlas/Build/
#export MA=~/MouseAtlas/Build/
export MA=/opt/MouseAtlas/
# set path = ("$MA"/bin $path)
export PATH="$MA"/bin:$PATH
# setenv LD_LIBRARY_PATH "$MA"/lib:$LD_LIBRARY_PATH
export LD_LIBRARY_PATH="$MA"/lib:$LD_LIBRARY_PATH

# Cleanup
#rm -rf nifticlib-2.0.0

# Unpack archive
#tar -zxf nifticlib-2.0.0.tar.gz

# Configure for use with Woolz making sure to use position independent
# code (using -fPIC for GCC or flags suitable for your compiller)
mkdir -p nifticlib-2.0.0-build
cd nifticlib-2.0.0-build
cmake -DBUILD_TESTING=Off \
      -DCMAKE_BUILD_TYPE=Release \
      -DCMAKE_C_FLAGS=-fPIC \
      -DCMAKE_INSTALL_PREFIX=$MA ../nifticlib-2.0.0

# Build
make

# Install
make install

# Cleanup
cd ..
#rm -rf nifticlib-2.0.0 nifticlib-2.0.0-build
