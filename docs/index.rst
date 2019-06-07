.. TraceR documentation master file, created by
   sphinx-quickstart on Mon Aug  6 16:00:19 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

TraceR documentation!
==================================

TraceR is a trace replay tool built upon the ROSS-based CODES simulation
framework. TraceR can be used for predicting network performance and
understanding network behavior by simulating messaging in High Performance
Computing applications on interconnection networks.

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   install
   userguide
   tutorial
   autogen/doxygen


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

Some useful options to use with TraceR:

--sync                 ROSS's PDES type. 1 - sequential, 2 - conservative, 3 - optimistic
--nkp                  number of groups used for clustering LPs; recommended value for lower rollbacks: (total #LPs)/(#MPI processes)
--extramem             number of messages in ROSS's extra message buffer (each message is ~500 bytes, 100K should work for most cases)
--max-opt-lookahead    leash on optimistic execution in nanoseconds (1 microsecond is a good value)
--timer-frequency      frequency with which PE0 should print current virtual time
