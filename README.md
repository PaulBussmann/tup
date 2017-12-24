# Tup

http://gittup.org/tup

## About Tup

Tup is a file-based build system for Linux, OSX, and Windows. It takes
as input a list of file changes and a directed acyclic graph (DAG). It
then processes the DAG to execute the appropriate commands required to
update dependent files. Updates are performed with very little overhead
since tup implements powerful build algorithms to avoid doing
unnecessary work. This means you can stay focused on your project rather
than on your build system.

Further information can be found at http://gittup.org/tup

# Building Tup

## On Linux for MinGW (Windows)

The following steps were tested on Ubuntu 17.10

```
# install required packages
sudo apt install git pkg-config gcc libfuse-dev gcc-mingw-w64-i686 gcc-mingw-w64-x86-64
git clone https://github.com/PaulBussmann/tup.git
cd tup

# bootstrap native tup, lua
./build.sh
mkdir build-tup-linux
cp build/tup build/lua build-tup-linux/
export PATH=$PWD/build-tup-linux:$PATH

# cross compile for MinGW
git checkout BuildForMinGW
tup
```
