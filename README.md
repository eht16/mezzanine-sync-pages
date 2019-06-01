mezzanine-sync-pages
====================

[![Travis CI](https://travis-ci.org/eht16/mezzanine-sync-pages.svg?branch=master)](https://travis-ci.org/eht16/mezzanine-sync-pages)
[![PyPI](https://img.shields.io/pypi/v/mezzanine-sync-pages.svg)](https://pypi.org/project/mezzanine-sync-pages/)
[![Python Versions](https://img.shields.io/pypi/pyversions/mezzanine-sync-pages.svg)](https://pypi.org/project/mezzanine-sync-pages/)
[![License](https://img.shields.io/pypi/l/mezzanine-sync-pages.svg)](https://pypi.org/project/mezzanine-sync-pages/)

mezzanine-sync-pages let you synchronize the contents of pages
in Mezzanine.
This comes in handy if you want to manage your page contents
as plain text/HTML files rather than in a web editor and if you
want to manage your content in a version control system like Git.

It does synchronize *only* the page contents and not any metadata
(like title, slug, publish date, ...).

To create an initial dump of all existing pages in Mezzanine you can
use the management command `dump_pages`.
To write back the previously dumped (and maybe modified) contents, use
the `sync_pages` management command or the corresponding action in the
admin interface.

### Features:

- Dump contents of all pages in Mezzanine as files
- Write back page contents to Mezzanine
- Detect unmodified content and skip those pages
- Display a diff on modified content after updating


Installation
------------

The easiest method is to install directly from pypi using pip:

    pip install mezzanine-sync-pages


If you prefer, you can download mezzanine-sync-pages from
https://github.com/eht16/mezzanine-sync-pages and install it directly from source:

    python setup.py install


Get the Source
--------------

The source code is available at https://github.com/eht16/mezzanine-sync-pages/.


Configuration
-------------

- Add `mezzanine_sync_pages` to `INSTALLED_APPS`

- Set `MEZZANINE_SYNC_PAGES_DESTINATION_PATH` in your settings.py to the path
  where the content files can be found


Usage
-----

After activating the app, two new management commands are added:

- `dump_pages`: create an initial dump of all pages in Mezzanine and
                write the corresponding files in `MEZZANINE_SYNC_PAGES_DESTINATION_PATH`

- `sync_pages`: read all files from `MEZZANINE_SYNC_PAGES_DESTINATION_PATH` and write their
                content to Mezzanine

Additionally, a new action in the Mezzanine admin interface is added to trigger the
synchronization of the pages to Mezzanine.


ChangeLog
---------

### 1.0.0 / 2019-06-01

- Initial release


License
-------
mezzanine-sync-pages is licensed under the MIT license.


Author
------

Enrico Tröger <enrico.troeger@uvena.de>
