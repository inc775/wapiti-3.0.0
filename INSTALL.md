Introduction
============

All installation methods assume you already have a Python 3.4 or more recent on your system.

Note that if you have all the requirements pre-installed on your system, it is not necessary to use the setup.py script
to use Wapiti : just extract the archive and launch the "wapiti" command line in the "bin" folder :

 `./bin/wapiti` or `python bin/wapiti`.

You may want to install Wapiti to the system just to make access easier.  
If you haven't sufficient privileges are you are afraid of beaking some dependencies in your python packages then
using a virtual environment is the way to go. Just refer to the related section.

Otherwise you will have to launch setup.py as a privileged user.

Enjoy Wapiti.


Libxml2 dependancy
==================

The hard part of the installation may be to get libxml (plus development files) on your system.
Libxml2 is the parser used by default in Wapiti. It's fast hence recommended.

Installation commands for several operating systems can be found above.  
If the installation fails at some point you can opt-out by giving the --with-html5lib option to the setup.py script.  
This way Wapiti will rely on html5lib (another parser, lenient but slower) instead.  
Feel free to report every installation problem. 


Setting up a virtual environment for Wapiti
===========================================

Let's create a virtual environment called 'wapiti3'.  
In this example it will be created in the current working directory.

`python -m venv wapiti3`

Now let's activate it (make it our current working environnement) :
 
`. ./wapiti3/bin/activate`

Or alternatively on Windows :

`wapiti3\Scripts\activate.bat`

Now you are in the virtual environment you can install Wapiti and its dependencies :

`python3 setup.py install`

To leave the virtual environnement just call the following command :

`deactivate`

Remember that you will need to reactivate the environment each time you want to use Wapiti. 


Libxml2 installation on Ubuntu 16.04.3 or Kali Linux
====================================================
sudo apt-get install python3-venv libxml2 libxml2-dev libz-dev libxslt1-dev python3-dev

Full video tutorial: https://www.youtube.com/watch?v=TD5rehelHPY

Libxml2 installation on opensuse Leap
=====================================
sudo zypper install libxml2-2 libxml2-devel libxslt1 libxslt-devel gcc python3-devel

Full video tutorial: https://www.youtube.com/watch?v=RmF2Sr2B3ZA

Libxml2 installation on Arch Linux
==================================
sudo pacman -S libxml2

Libxml2 installation on Fedora
==============================
sudo yum install gcc libxml2-devel libxslt-devel redhat-rpm-config python3-devel


Libxml2 installation on Windows
===============================

Full video tutorial: https://www.youtube.com/watch?v=j3LCVj15VBE

First make sure you have installed python3 on your computer and that path to the installation path was added
to your PATH environment variable (Python installer should do that by default).

Installing libxml2 on Windows would normally require downloading and installing several gigabytes
of MS development tools with much pain.

Fortunately some non-official pre-built Python extensions for lxml are available.  
Download the appropriate whl file for lxml from the following webpage :

https://www.lfd.uci.edu/~gohlke/pythonlibs/#lxml

Make sure to download to good wheel archive. For example if you are using Python 3.6 on a 64bits
architecture then to good wheel file should be lxml‑4.1.1‑cp36‑cp36m‑win_amd64.whl.

Then install the wheel file using pip (adjust the name of the file based on your needs):

`pip3 install lxml‑4.1.1‑cp36‑cp36m‑win_amd64.whl`

That's it !


Installing Wapiti
=================

Now that libxml2 is installed on the system you just have yo install wapiti this way :

`python setup.py install`

Or if you skipped the libxml2 installation :

`python setup.py install --with-html5lib`