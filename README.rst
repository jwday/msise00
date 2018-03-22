.. image:: https://zenodo.org/badge/32971905.svg
   :target: https://zenodo.org/badge/latestdoi/32971905
   
.. image:: https://travis-ci.org/scivision/msise00.svg
    :target: https://travis-ci.org/scivision/msise00
    
.. image:: https://coveralls.io/repos/scivision/msise00/badge.svg?branch=master&service=github 
   :target: https://coveralls.io/github/scivision/msise00?branch=master 
   
.. image:: https://api.codeclimate.com/v1/badges/f6f206d6f6605bcf435d/maintainability
   :target: https://codeclimate.com/github/scivision/msise00/maintainability
   :alt: Maintainability


==========
msise-00
==========
NRL MSISE-00 atmospheric model.  
Valid from altitude z = 0 - 1000 km.

The plot immediately below shows a slice at 200km on a world-wide grid.
The yellow ball represents the sun footprint on Earth.

.. image:: tests/msise00_demo.gif

Install
=======
**NOTE:** It is advisable to have a Python package of your choosing already installed. Anaconda, for example, comes with all of the packages used in msise00. Furthermore, this package will be installed using Python 3 commands. Linux (and Windows Subsystem for Linux) default to Python 2.7 in the Command Line Interface (CLI), but 2.7 is going the way of the dinosaur and we like to look forward, not backward.

If you don't already have pip (a Python package manager that lets you install other packages) installed::
    sudo apt-get install python-pip

If you don't already have Numpy::

    pip3 install numpy
    pip3 install pandas
    pip3 install python-dateutil
    pip3 install matplotlib



Clone the repository ::

    git clone <repo_URL>


Since this is not a works-out-of-the-box solution, you must first build the package. This is necessary since the original model was written in FORTRAN, whereas we're trying to use it in Python. In other words, we have to sort of "wrap" some Python code around the FORTRAN code, and the results will be different depending on what operating system you're running. So be sure you're in the same directory that you cloned the repository to, then run the following:

* Mac: ``brew install gcc``
* Linux: ``sudo apt-get update && sudo apt-get install gfortran``
* `Windows <https://www.scivision.co/windows-gcc-gfortran-cmake-make-install/>`_
* Alternatively for Windows: Use Windows Subsystem for Linux, then follow the Linux installation instructions


Install msise00 ::

    pip3 install -e .
    
* Be sure you're in the msise00 directory when running pip install -e
  
  
  

Examples:
---------
Output time series of PNGs to your temp directory::

  python DemoMSIS.py

Reference
=========
`Original fortran code <http://nssdcftp.gsfc.nasa.gov/models/atmospheric/msis/nrlmsise00/>`_

`1200+ citations 2002 paper <http://onlinelibrary.wiley.com/doi/10.1029/2002JA009430/pdf>`_
