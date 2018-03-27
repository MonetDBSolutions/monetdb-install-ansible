Ansible scripts to install MonetDB in various ways
==================================================

Install MonetDB in one of the following ways

- from distribution packages (rpm, deb) downloaded from
  [monetdb.org](https://www.monetdb.org/downloads/)

- built from source downloaded from
  [monetdb.org](https://www.monetdb.org/downloads/sources/)

- built from source cloned from the [MonetDB mercurial
  repository](https://dev.monetdb.org/hg/MonetDB/)

Roles
-----

`monetdb_package`.  Installs MonetDB on Linux using the appropriate package
manager.

`monetdb_source`. Installs MonetDB from source.

`monetdb_farm`. Creates and starts DB Farm.

Settings
--------

`monetdb_release`. Release name such as 'Jul2017-SP4'.

`monetdb_version`. Version number such as 11.27.13. Can sometimes be derived
from `{{monetdb_release}}`.

`monetdb_prefix`. MonetDB's `bin`, `lib`, etc. directories will be created
under this directory when installing from source.

`monetdb_src`. Where to put the MonetDB source code when installing from
source. Defaults to `{{monetdb_prefix}}/src`.

`build_dir`. Where to build MonetDB when installing from source. Defaults to
`{{monetdb_prefix}}/build`.

`hg_revision`.  Mercurial revision to check out. If this is set the download
will be performed with `hg clone` and the `monetdb_release` and
`monetdb_version` settings will be ignored.

`dbfarm dir`.  If set, a dbfarm will be created and started in this location.

`can_sudo`. If set to false no attempt will be made to install dependencies
such as bison, gettext and openssl.

`force_build`.  If set, MonetDB is (re)compiled and (re)installed even if
it already seems to exist.

`monetdb_configure_flags`.  Flags to pass to `configure`.  Defaults to
`--enable-optimize --disable-debug --disable-assert --disable-developer`.
