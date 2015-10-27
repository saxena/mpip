# mpiP-mm
mpiP - Minimal Metrics edition

This is modification of the fantastic MPI performance tracing library that is [mpiP](http://mpip.sourceforge.net). These changes were made on behalf of Sandia National Laboratories by Minimal Metrics LLC. More features will be added as required.

Specifically, this branch of mpiP makes the following modifications:

* Rank-specific MPI time data
* Point to point profiling of "Bytes" and "MPI Time"
  between pairs of source and destination ranks

This software is based on the Version 3.4.1, 13 March 2014, of mpiP.

## How to use this software

### Compiling

* Clone this:

`git clone https://<you>@bitbucket.org/minimalmetrics/mpip.git`

* Build that, MM-style:

```
./configure --disable-bfd --disable-libunwind --disable-so-lookup --disable-fortranxlate
make
make test
make shared
```

* Test it:

`cd testing`
`mpirun -np 2 ./9-test-mpip-time.exe`

* Test the new code:

`export MPIP=-q`
`mpirun -np 2 ./9-test-mpip-time.exe`

* Dependencies:

Any platform where mpiP, Version 3.4.1, 13 March 2014 can be built and passes all testing (which is virtually everywhere).

### Usage

To Enable Rank Specific MPI Time information and to enable Rank to Rank Bytes and MPI Time details use the '-q' option to the MPIP env variable, or add this flag to your current set of MPIP options

`export MPIP=-q`

## Compiling for Intel Xeon Phi (MIC)

General Instructions for MIC Programming are located at https://software.intel.com/en-us/mic-developer/programming

General Instructions for compiling applications for MIC are located at https://software.intel.com/en-us/articles/building-a-native-application-for-intel-xeon-phi-coprocessors

General Instructions for compiling Intel MPI Library are located at https://software.intel.com/en-us/articles/using-the-intel-mpi-library-on-intel-xeon-phi-coprocessor-systems

*Source Intel Compiler Variables

`source /mnt/scratch/sw/intel/composerxe/bin/compilervars.sh intel64`

*Source Intel MPI Environment

`source /mnt/scratch/sw/intel/impi_latest/mic/bin/mpivars.sh`
 
*Building:

```
$ ./configure --disable-bfd --disable-libunwind --disable-so-lookup --disable-fortranxlate --with-cc=mpiicc --with-cxx=mpiicpc --with-f77=mpiifort CFLAGS="-g -O2 -mmic" FFLAGS="-g -mmic" LDFLAGS="-mmic -L /mnt/scratch/sw/intel/composer_xe_2015.3.187/compiler/lib/mic"
$ make
$ make test
```

*Testing code

```
$ export SINK_LD_LIBRARY_PATH=/mnt/scratch/sw/intel/impi/5.0.3.048/mic/lib
$ micnativeloadex ./9-test-mpip-time.exe -l
$ micnativeloadex ./9-test-mpip-time.exe
```

