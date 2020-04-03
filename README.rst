This readme file is the "msise00 for dummies" version. For those of us who didn't study computer science and don't speak Python/C++/FORTRAN/HTML/CSS/javascript/KOBOL as a second language(s), hopefully this will help clear the mud.

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

If you don't already have Python 3 ::

    add-apt-repository ppa:deadsnakes/ppa
    apt-get update
    apt-get install python3.7

Alternatively, just install Anaconda because it's awesome.

Follow the instructions at https://docs.anaconda.com/anaconda/install/linux/



pip (a Python package manager that lets you install other packages) should already come installed with Python. To see if you have it ::

    command -v pip


In case you don't have pip ::

    apt-get install python-pip
    pip install --upgrade pip



Once pip is installed, there are a number of other packages that are needed to run msise00. If you don't already have the following packages, install them ::

    pip install numpy
    pip install pandas
    pip install python-dateutil
    pip install matplotlib
    pip install scipy
    pip install seaborn
    pip install astropy
    pip install pymap3d
    pip install gridaurora


You will also need a FORTRAN compiler to...compile. Try this one ::

    sudo apt-get install gfortran


Furthermore, you will also need a builder to...build. Try this one ::

    sudo apt-get install cmake



Now with everything installed, lets get to work on msise00. Start by clone the repository into a directory of your choice ::

    git clone <repo_URL>


Since this is not a works-out-of-the-box solution, you must first build the package. This is necessary since the original model was written in FORTRAN, whereas we're trying to use it in Python. In other words, we have "wrap" some Python code around the FORTRAN code, and the process will be different depending on what operating system you're running. So be sure you're NOT in the directory that you cloned the repository to, then run the following:

* Mac: ``brew install gcc``
* Linux: ``sudo apt-get update && sudo apt-get install gfortran``
* `Windows <https://www.scivision.co/windows-gcc-gfortran-cmake-make-install/>`_
* Alternatively for Windows: Use Windows Subsystem for Linux, then follow the Linux installation instructions. This is the preferred method for Windows, but requires the user to have already set up Windows Subsystem for Linux (this author uses Ubuntu and acquired it from the Microsoft Store app).


Install msise00 ::

    git clone https://github.com/space-physics/msise00

    python -m pip install -e msise00

* Be sure you're NOT in the msise00 directory when running pip install -e
  


 

Examples:
---------
Output time series of PNGs to your temp directory::

  python DemoMSIS.py

Reference
=========
`Original fortran code <http://nssdcftp.gsfc.nasa.gov/models/atmospheric/msis/nrlmsise00/>`_

`1200+ citations 2002 paper <http://onlinelibrary.wiley.com/doi/10.1029/2002JA009430/pdf>`_
