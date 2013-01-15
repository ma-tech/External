#!/bin/sh
# \file		README.Qtcolorpicker		
# \author	Bill Hill
# \date		April 2010
# \version	$Id$
#
# To build QtColorPicker see qtcolorpicker-2.6-opensource/INSTALL.TXT,
# or in brief:

set -x

rm -rf qtcolorpicker-2.6-opensource
rm -f  qtcolorpicker

tar -zxf qtcolorpicker-2.6-opensource.tar.gz
ln -s qtcolorpicker-2.6-opensource qtcolorpicker
cd qtcolorpicker
./configure
qmake
make

