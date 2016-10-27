#!/usr/bin/env python

import sys, os
from docutils.core import publish_file

if len(sys.argv) == 2:
    infile = sys.argv[1]+".rst"
    outfile = sys.argv[1]+".html"
elif len(sys.argv) == 3:
    infile = sys.argv[1]
    outfile = sys.argv[2]
else:
    print "rst 0.5 -- convert reStructuredText to HTML"
    print "Usage: rst <in_rst_file> <out_html_file>"
    print "   or: rst <filename_without_ext>"
    print "Env vars:"
    print "  STYLE : css stylesheet path"
    sys.exit(2)

settings_overrides={
    'field_name_limit': 40,
    }

if 'STYLE' in os.environ:
    settings_overrides['stylesheet_path'] = os.environ['STYLE']
else:
    settings_overrides['stylesheet_path'] = os.path.realpath(os.path.join(os.path.dirname(os.path.abspath(__file__)), "stylesheet.css"))

publish_file(source_path=infile,
             destination_path=outfile,
             settings_overrides=settings_overrides,
             writer_name='html')
