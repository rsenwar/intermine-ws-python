The InterMine Python Webservice Client
=====================================

[![Build Status][badge]][ci] 
[![Conda](https://anaconda.org/intermine/intermine/badges/installer/conda.svg)](https://anaconda.org/intermine/intermine)

An implementation of a webservice client 
for InterMine webservices, written in Python

Who should use this software?
-----------------------------

This software is intended for people who make 
use of InterMine datawarehouses (ie. Biologists)
and who want a quicker, more automated way 
to perform queries. Some examples of sites that
are powered by InterMine software, and thus offer
a compatible webservice API, are:

* FlyMine
* HumanMine
* MouseMine
* RatMine
* YeastMine
* ZebrafishMine

Queries here refer to database queries over the 
integrated datawarehouse. Instead of using 
SQL, InterMine services use a flexible and 
powerful sub-set of database query language
to enable wide-ranging and arbitrary queries.

Requirements
------------
This package is compatible with both Python 2.7 and 3.x.  It may be compatible with older versions of Python 2 but this is untested.

Downloading:
------------

The easiest way to install is to use easy_install:

  sudo easy_install intermine

The source code can be downloaded from a variety of places:

* From InterMine

  wget http://www.intermine.org/lib/python-webservice-client-0.96.00.tar.gz

* From PyPi

  wget http://pypi.python.org/packages/source/i/intermine/intermine-0.96.00.tar.gz

* From Github

  git clone git://github.com/alexkalderimis/intermine-ws-python.git


Running the Tests:
------------------

If you would like to run the test suite, you can do so by executing
the following command: (from the source directory)

  python setup.py test

Installation:
-------------

Once downloaded, you can install the module with the command (from the source directory):

  python setup.py install

Further documentation:
----------------------

Extensive documentation is available by using the "pydoc" command, eg:

  pydoc intermine.query.Query

Also see:

* Documentation on PyPi: http://packages.python.org/intermine/

License:
--------

All code in this project is dual licensed under the LGPL version 3 license and the BSD 2-clause license

Changes:
--------

    1.09.09   Add Python 3 support
    1.09.06   Dual license under BSD as well as LGPL
    1.07.00   Provide ListManagers as context managers, where users need to create
              temporary lists and clean up after themselves.
              Added ID resolution.
    1.05.00   Allowed constraints to be added on root paths implicitly, eg:
              q.where('LOOKUP', 'eve') or q.where('IN', 'My List')
    1.01.00   Added widget listing requests.
    1.00.00   Added widget enrichment requests.
    0.99.08   Added simpler constraint definition with kwargs.
    0.99.07   Fixed bugs with lazy reference fetching handling empty collections and null references.
    0.99.06   Fixed bug whereby constraint codes in xml were being ignored when queries were deserialised.
    0.99.05   Allow template parameters of the form 'A = "zen"', where only the value is being replaced.
    0.99.04   Merged 'list.to_query and 'list.to_attribute_query' in response to the changes in list upload behaviour.
    0.99.03   Allow query construction from Columns with "where" and "filter"
              Allow list and query objects as the value in an add_constraint call with "IN" and "NOT IN" operators.
              Ensure lists and queries share the same overloading
    0.99.02   Allow sort-orders which are not in the view but are on selected classes
    0.99.01   Better representation of multiple sort-orders.
    0.99.00   Fixed bug with subclasses not being included in clones 
              Added support for new json format for ws versions >= 8.
    0.98.16   Fixed bug with XML parsing and subclasses where the subclass is mentioned in the first view.
              better result format documentation and tests
              added len() to results iterators
              added ability to parse xml from the service object (see new_query())
              improved service.select() - now accepts plain class names which work equally well for results and lists
              Allowed lists to be generated from queries with unambiguous selected classes.
              Fixed questionable constraint parsing bug which lead to failed template parsing
    0.98.15   Added lazy-reference fetching for result objects, and list-tagging support
    0.98.14   Added status property to list objects
    0.98.13   Added query column summary support

[badge]: https://travis-ci.org/alexkalderimis/intermine-ws-client.py.svg?branch=master
[ci]: https://travis-ci.org/alexkalderimis/intermine-ws-client.py

