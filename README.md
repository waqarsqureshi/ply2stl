# ply2stl for Linux (Ubuntu 14.04)

This converter depends on vcg library. It will also help how to use vcg library and how to convert to other formats supported by vcg library

This code converts ply file to stl file using vcg library

# Download the vcg library 
svn checkout svn://svn.code.sf.net/p/vcg/code/trunk/vcglib vcglib
# Download this source code
git clone <path to the git sourcecode>

# Set the path of VCG library in the CMAKEList.txt
set(VCG_INCLUDE_DIR /home/te5100server1/vcglib/)

# Use CMAKE GUI to create a Makefile for your project
