.. image:: https://github.com/openturns/otwrapy/actions/workflows/build.yml/badge.svg?branch=master
    :target: https://github.com/openturns/otwrapy/actions/workflows/build.yml

`otwrapy` is a collection of tools that simplify the task of wrapping
external codes in a Python environment as well as parallelizing it. It is built
on top of `OpenTURNS <http://www.openturns.org>`_, with its users as the target
audience. Documentation is available
`here <http://openturns.github.io/otwrapy/master>`_. The module provides :

- An integrated progress bar for unit evaluation of a sample without parallelization.
- A `Parallelizer` class that converts any
  `ot.Function <http://openturns.github.io/openturns/master/user_manual/_generated/openturns.Function.html>`_
  into  a parallel wrapper using either
  `multiprocessing <https://docs.python.org/2/library/multiprocessing.html>`_,
  `ipyparallel <http://ipyparallel.readthedocs.io/en/latest/>`_,
  `joblib <https://pythonhosted.org/joblib/>`_,
  `pathos <https://pypi.python.org/pypi/pathos>`_,
  `dask SSHCluster <https://docs.dask.org/en/latest/deploying-ssh.html>`_ or
  `dask_jobqueue SLURMCluster <https://jobqueue.dask.org/en/latest/generated/dask_jobqueue.SLURMCluster.html>`_.
- A set of useful tools that simply recurrent tasks when writing code
  wrappers:

  - `TempWorkDir`: Context manager that gracefully creates a temporary
    working directory. It handles errors and has the option to cleanup upon
    exit.
  - `Debug`: Decorator that protects the decorated function into a
    try/except structure so that errors are logged. It is specially useful
    when you launch your code in a non interactive environment.
  - `load_array` and `dump_array`: Used for efficiently create
    and load backups with the option to compress with gzip.
  - `safemakedirs`: Create a directory without raising an exception if
    it exits.
  - `create_logger`: Return a logger with a FileHandler at a given
    logging level.

`otwrapy` comes from the experience of wrapping a lot of
different external codes at `Phimeca engineering
<http://www.phimeca.com>`_. We are a company specialized in
uncertainty treatment and we assist our clients introducing the
probabilistic dimension in their so far deterministic studies.
