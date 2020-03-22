To compile with only multicore CPU support, execute
```bash
sudo apt-get install hwloc libhwloc-dev
./autogen.sh # If compiling from scratch.
mkdir build && cd build
CFLAGS=-fPIC CPPFLAGS=-fPIC CXXFLAGS=-fPIC FFLAGS=-fPIC \
FCFLAGS=-fPIC ../configure --prefix=${PWD}
make && make install
```
Ensure the following environment variables are set when using the library:
```bash
export OMP_CANCELLATION=TRUE
export OMP_NESTED=TRUE
export OMP_PROC_BIND=TRUE
```
