Model-logger
============

.. figure:: https://github.com/SohamPathak/modellogger.github.io/blob/master/assets/logo-header.png
   :alt: Pandas Profiling Logo Header

   Pandas Profiling Logo Header

Modelloger is a Python library for storing model’s profile and rapid
inter model comparision. Powered by dash and SQLITE3, It’s compact
,light and interactive yet powerfull tool to gain usefull insights.

Installation
------------

Using pip
~~~~~~~~~

Use the package manager `pip`_ to install modelloger.

|PyPi Downloads| |PyPi Monthly Downloads| |PyPi Version|

.. code:: bash

   pip install modellogger

Usage
-----

.. code:: python

   from modellogger import ModelLogger

   #initialise a modelloger instance
   path = "c/path/to/db/databasename.db"
   mlog = ModelLogger(path)
    
   #If you are already using a db created by modelloger you can directly load it by stating it's path
   #if you are creating a new project just give location where you want to store the db followed by a name.db  

Contributing
------------

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

License
-------

`apache-2.0`_

.. _pip: https://pip.pypa.io/en/stable/
.. _apache-2.0: https://choosealicense.com/licenses/apache-2.0/

.. |PyPi Downloads| image:: https://pepy.tech/badge/modellogger
   :target: https://pepy.tech/badge/modellogger
.. |PyPi Monthly Downloads| image:: https://pepy.tech/badge/modellogger/month
   :target: https://pepy.tech/badge/modellogger/month
.. |PyPi Version| image:: https://badge.fury.io/py/modellogger.svg
   :target: https://pypi.org/project/modellogger/