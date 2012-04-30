# PyArnoldi

Arnoldi algorithm in Python and C++ (with Python link)

## Dependencies:

 * Eigen matrix library (http://eigen.tuxfamily.org)
 * boost::python (http://www.boost.org/doc/libs/1_48_0/libs/python)

### Debian

 * Eigen matrix library in packet "libeigen3-dev"
 * boost::python in packet "libboost-python1.46-dev"
   (At this time the version 1.46 is the most recent one from sid.)

### Brutus
The following brutus modules must be loaded for the compilation to work:

 * module load python/2.7.2
 * module load boost

Additionally, the library path must be updated:

 * export LD_LIBRARY_PATH=/cluster/apps/boost/1_47_0_nompi/x86_64/gcc_4.1.2/lib64:$LD_LIBRARY_PATH


## Compilation:

 * edit the makefile to contain your correct library paths
 * `make python` to compile the python module
 * `make prog` to compile a small test program

## Usage:

 * test_arnoldi.py: unit tests using nose.
   install python-nose and run "nosetests" from the console
 * demo_arnoldi.py: timing script which calls Python and C++ versions
   for various N and plots the resulting times.
 * to directly use in python, just compile (make python) and run:

   >>> import arnoldi
   >>> arnoldi.arnoldi(A,v,k,V,H)

