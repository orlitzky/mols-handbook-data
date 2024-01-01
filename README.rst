Python interface to the Mutually Orthogonal Latin Squares (MOLS) data
in the Handbook of Combinatorial Designs

Introduction
============

The Handbook of Combinatorial Designs (2nd edition) by Colbourn and
Dinitz contains a Table 3.87 with the known lower bounds on the number
of MOLS of a given order. The table is a simple one-dimensional index
on the order `n` of the square, and contains entries for order `n=0`
up to order `n=9999`.

This package consists of a single module containing a single public
function, ``lower_bound()``, that returns the lower bounds from the
table. It takes one argument, the order (also known as the *side*)
``n`` of the MOLS.

This is the successor of the SageMath *combinatorial_designs*
package:

  http://files.sagemath.org//spkg/upstream/combinatorial_designs/

Examples
========

It's hard to misuse this package::

  >>> from mols_handbook_data import lower_bound
  >>> lower_bound(1234)
  8

The worst thing that can happen is an ``IndexError``, if you ask for
an order that isn't contained in the table::

  >>> from mols_handbook_data import lower_bound
  >>> lower_bound(12345)
  Traceback (most recent call last):
  ...
  IndexError: tuple index out of range

Testing
=======

A few doctests within the module (and this README) ensure that
everything is working. You can run them from the repository or from a
release tarball using::

  PYTHONPATH=src python -m doctest \
    README.rst \
    src/mols_handbook_data/__init__.py
