===================
Packaging your game
===================

When creating a game for PyWeek, you will want to be sure that it can be played
by the most people possible.

Below are some tips that you should follow.


Zip the source
--------------

According to :ref:`rule 7 <final-submission>`, your game must include all
source code.

This is the first thing you should do. Packaging a game for various platforms
(eg. using PyInstaller) is entirely optional - including the source is not.

It is recommended to create a ZIP file that contains your source code. ZIP
files can be read on almost all operating systems with standard software.


.. tip::

    Check that your game runs from the ZIP file you create. A common mistake
    is to fail to include some file that your game depends on!


Each ZIP file should contain a top-level directory, named after your game. If
you are using version numbers for your game, the top level directory should
also have the same name.

So if my game is *Camel Breeder*, I might create a ZIP file called
``Camel-Breeder-1.0.zip``, containing a directory ``Camel-Breeder-1.0``.

.. caution::

    Don't create a `Zip bomb`_, which creates many files in the directory
    where you unzip it.


.. _`Zip bomb`: https://en.wikipedia.org/wiki/Zip_bomb


Include a run_game.py
---------------------

Something that has become a convention in PyWeek is to have a file in your game
source called ``run_game.py``, which runs your game.

This makes it easy for people to see how to run your game, no matter how you
decide to structure the code for your game.


.. tip::

    Your Python code may not be compatible with older (or newer) Python
    interpreters. But the judges may not guess correctly which interpreter
    version they should use to run your game.

    A good tip is to make sure your ``run_game.py`` exits quickly with an
    informative error if people are using the wrong Python interpreter.

    Put this code at the top of ``run_game.py`` (replace ``(3, 7)`` with the
    version you actually require)::

        import sys

        # The major, minor version numbers your require
        MIN_VER = (3, 7)

        if sys.version_info[:2] < MIN_VER:
            sys.exit(
                "This game requires Python {}.{}.".format(*MIN_VER)
            )

    (Note that this file must be compatible with all old syntax. The above
    code is compatible with Python 2.6 and later.)


Include a README
----------------

Include a ``README`` file in all your packages. This is the perfect place to
explain:

* What dependencies your game requires to run
* How to build and run your game
* The controls
* What there is to see in the game
* Copyright attributions (eg. CC-BY resources you have used)



Building executable files
-------------------------

Once you have created and uploaded a source distribution, you can, if you wish,
try creating an executable so that people will be able to run your game without
having a Python interpreter installed.

The recommended tool for doing this, for all platforms, is PyInstaller_. The
full manual for PyInstaller is here__.

Older tools, such as cx_freeze_, py2exe_ and py2app, are not recommended. These
each target only one operating system, and seem to be unmaintained (as of
2019).


.. _PyInstaller: https://www.pyinstaller.org/
.. __: https://pyinstaller.readthedocs.io/en/stable/
.. _cx_freeze: https://cx-freeze.readthedocs.io/en/latest/index.html
.. _py2exe: http://www.py2exe.org/
