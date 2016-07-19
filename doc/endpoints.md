Endpoints for the API
=====================

The Open Source API contains metadata regarding OSI Approved Licenses,
and crosswalks that help with using and integrating this information
with external sources. You can think of this API as a sort of "hub" or
"connector" to help ensure end users can simply build applications that
are license-aware.

Get a list of all licenses
--------------------------

### `/licenses/`

 - e.g., https://api.opensource.org/licenses/

Get a list of all known licenses.

### `/licenses/<keyword>`

 - e.g., https://api.opensource.org/licenses/copyleft

 Find all licenses by a `keyword` (defined below).

Get a license
-------------

### `/license/<id>`

 - e.g., https://api.opensource.org/license/GPL-3.0

Get a license by its OSI ID

### `/license/<scheme>/<identifier>`

 - e.g., https://api.opensource.org/license/SPDX/Apache-2.0

Get a license by an identifier (such as `SPDX/Apache-2.0` or `DEP5/Expat`)

Schema
======

Attribute documentation
-----------------------

attribute       | description
----------------|------------
`id`            | OSI Identifier (such as `MPL-2.0`)
`name`          | Name of the License (such as `General Public License`)
`superseded_by` | OSI Identifier of the licenses that supersedes this license (such as `EPL-1.0`)
`keywords`      | List of text keywords that describe this license. (see Keywords below)
`identifiers`   | List of identifier objects for this license (see Identifier below)
`links`         | List of link objects for this license (see Link below)
`other_names`   | List of other_name objects for this license (see Other Name)
`text`          | List of text objects for this license (see Text below)


Keywords
--------

keyword           | description
------------------|------------
`osi-approved`    | This license has been OSI Approved.
`redundant`       | This license is redundant with a more widely used license.
`permissive`      |
`copyleft`        | This license requires derived works remain Open Source.
`obsolete`        | This license is considered obsolete by its authors.
`miscellaneous`   |
`popular`         | This license is widely used.
`discouraged`     | This license's use is actively discouraged.
`non-reusable`    | This license isn't generally usable outside of the authoring organization.
`special-purpose` | This license suits a very special purpose.
`retired`         | This license has been retired.


Identifier
----------

attribute         | description
------------------|------------
`identifier`      | A text identifier issued for the `scheme` below.
`scheme`          | An identifier namespace (such as `SPDX` or `DEP5`)


Link
----

attribute         | description
------------------|------------
`note`            | Description of the link
`url`             | `URL` of the link


Other Name
----------

attribute         | description
------------------|------------
`name`            | Other name this license is known by
`note`            | Note regarding the use of this name

Text
----

attribute         | description
------------------|------------
`media_type`      | Type of content contained at the URL (sometimes called content type or MIME)
`title`           | Title of the text link
`url`             | URL to the text


API Wrappers
============

  - [python-opensource](https://github.com/opensourceorg/python-opensource) ([@paultag](http://github.com/paultag))
  - [ruby-opensourceapi](https://github.com/opensourceorg/ruby-opensourceapi) ([@paultag](http://github.com/paultag))
  - [haskell-opensource](https://github.com/OpenSourceOrg/haskell-opensource) ([@clinty](http://github.com/clinty))
  - [github.com/opensourceorg/api/client](https://github.com/OpenSourceOrg/api/tree/master/client) ([@paultag](http://github.com/paultag))
  - [rust-opensource](https://github.com/opensourceorg/rust-opensource) ([@eriol](https://github.com/eriol))
  - [ocaml-opensource](https://github.com/opensourceorg/ocaml-opensource) ([@mehdid](https://github.com/mehdid))

Contribute additional data
==========================

Don't see what you need? Send a pull request! The data provided in the API is
stored in Git, currently hosted on the
[opensourceorg/licenses](https://github.com/opensourceorg/licenses) repo.
Feel free to file bugs, help work on improvements, and send in pull requests!

Licensing
=========

Data provided by this API is licensed CC0.
