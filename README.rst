service\_utils
==============

A simple python package for quick and easy microservices logging and
configuration.

|Codacy Badge| |Build Status| |Version| |LICENSE|

Overview
--------

This package was created for fast and easy import in your application
functional which important as part of any service but not so fun for
developing each time. The most important thing for working with this
library is a configuration file. I especially use .ini format because it
is human-readable, simple to parse in python and disallow using large
multi-level configuration.

How to use it
-------------

How to use it in your repository
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

::

    1. Simple and good: `pip3 install service_utils`
    2. Simple and not so good: just copy service_utils.py in your repository
    3. Not so simple, but it allows you to have the last stable version of the library (if you really need): use .gitmodules file in your repository like this:

.gitmodules:

.. code:: bash

        [submodule "service_utils"]
            path = modules/service_utils
            url = https://github.com/Sid1057/service_utils.git
            branch = release

How to use it in your code
~~~~~~~~~~~~~~~~~~~~~~~~~~

Short answer
^^^^^^^^^^^^

.. code:: python

        from service_utils import Service_utils

        service_utils = Service_utils(
            '--config-key',
            configuration_required=True)

        # done

Real answer
^^^^^^^^^^^

Using your program as service mean that you will run it in some
operation system with some (maybe empty) arguments like:

.. code:: bash

        python3 my_app.py -config config.ini --use-something --print-anything

Using this package mean that you agree with my thinks about
configuration in applications and about part of a code which do this
stuff: 1. Configuration should be simple as possible. 2. Configuration
should be single in service. 3. Configuration package should do maximum
routine of posiible, but no more. 4. Configuration package should have
some default sections in the configuration file. 5. Configuration
package should allow a user (programmer) to do anything with
configuration. 6. Your application should have only one logger

Use

.. code:: python

        service_utils = Service_utils(
            '--config-key',  # this keyword would be expected when you run your application
            configuration_required=True,  # if True - you have to run your application only with config-key
            configuration_default_path='path_to_default_config.ini',  # if configuration is not required but default configuration exist - this path configuration to configuration file will be used
            description='This is description of application. It would be show in `python3 app.py --help`')

Also
~~~~

README is a little bit crap, but I work on it.

.. |Codacy Badge| image:: https://api.codacy.com/project/badge/Grade/819d6be760c04433a00dace98c674058
   :target: https://app.codacy.com/app/Sid1057/service_utils?utm_source=github.com&utm_medium=referral&utm_content=Sid1057/service_utils&utm_campaign=Badge_Grade_Dashboard
.. |Build Status| image:: https://travis-ci.com/Sid1057/service_utils.svg?branch=master
   :target: https://travis-ci.com/Sid1057/service_utils
.. |Version| image:: https://img.shields.io/pypi/v/service_utils.svg
   :target: https://pypi.org/project/service_utils/
.. |LICENSE| image:: https://img.shields.io/github/license/sid1057/service_utils.svg
   :target: https://github.com/Sid1057/service_utils/blob/master/LICENSE
