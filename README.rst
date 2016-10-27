rst
===

A Python script for converting rst files into html. Primary purpose of this 
script is to make review of rst patches easier

Usage
-----

Generate README.html from README.rst using the default stylesheet:

  $ STYLE=stylesheet.css ./rst README

The HTML file will be created to the directory where the rst file is, so you can 
point the script to any absolute or relative path:

  $ STYLE=stylesheet.css ./rst /home/john/tap-windows6/README

This command will produce */home/john/tap-windows6/README.html*.


License
-------

This utility is licensed under the BSD license. See file `LICENSE <LICENSE>`_
for details.
