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

`git clone https://rahulsaxena@bitbucket.orgminimalmetrics/mpip.git`

* Build that:

`make install-mpip`

* Dependencies:

Any platform where mpiP, Version 3.4.1, 13 March 2014 can be built and passes all testing (which is virtually everywhere).

### Usage

* Enable new features:

To Enable Rank Specific MPI Time information and to enable  Rank to Rank Bytes and MPI Time details use the '-q' option to the MPIP env variable (or add this flag to your current set of MPIP options):

`export MPIP=-q`
