User Guide
==========

Below, we provide detailed instructions for how to start doing network
simulations using TraceR.

Quickstart
----------

This is a basic ``mpirun`` command to launch a TraceR simulation in the
optimistic mode::

    mpirun -np <p> ../traceR --sync=3  -- <network_config> <tracer_config>

Some useful options to use with TraceR:

--sync                 ROSS's PDES type. 1 - sequential, 2 - conservative, 3 - optimistic
--nkp                  number of groups used for clustering LPs; recommended value for lower rollbacks: (total #LPs)/(#MPI processes)
--extramem             number of messages in ROSS's extra message buffer (each message is ~500 bytes, 100K should work for most cases)
--max-opt-lookahead    leash on optimistic execution in nanoseconds (1 microsecond is a good value)
--timer-frequency      frequency with which PE0 should print current virtual time

Creating a TraceR configuration file
------------------------------------

This is the format for the TraceR config file::

    <global map file>
    <num jobs>
    <Trace path for job0> <map file for job0> <number of ranks in job0> <iterations (use 1 if running in normal mode)>
    <Trace path for job1> <map file for job1> <number of ranks in job1> <iterations (use 1 if running in normal mode)>
    ...
    <Trace path for jobN> <map file for jobN> <number of ranks in jobN> <iterations (use 1 if running in normal mode)>


If you do not intend to create global or per-job map files, you can use ``NA``
instead of them.

Sample TraceR config files can be found in examples/jacobi2d-bigsim/tracer_config (BigSim) or examples/stencil4d-otf/tracer_config (OTF)
