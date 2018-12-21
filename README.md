# Demo QuickFIX

Demonstration of QuickFIX financial server:

* http://www.quickfixengine.org

* http://www.quickfixengine.org/quickfix/doc/html/building.html

* Using Amazon Web Services (AWS) EC2 server and Amazon Linux 1


## Download

Download:

```sh
$ curl -ssLO http://prdownloads.sourceforge.net/quickfix/quickfix-1.15.1.tar.gz
$ unzip quickfix-1.15.1.tar.gz
$ cd quickfix
```


## Bootstrap

Bootstrap:

```sh
$ ./bootstrap
```

If you get this error:

```sh
+ case `uname` in
++ uname
+ libtoolize --copy
./bootstrap: line 9: libtoolize: command not found
```

Then install libtool:

```sh
sudo yum install libtool
```

If you get this errors:

```sh
libtoolize: `m4/libtool.m4' is newer: use `--force' to overwrite
libtoolize: `m4/ltoptions.m4' is newer: use `--force' to overwrite
libtoolize: `m4/ltversion.m4' is newer: use `--force' to overwrite
```

Then that's ok for now.

Retry as needed.


## Configure

Run:

```sh
./configure
```

If you get this error:

```sh
configure.ac:34: warning: cannot check for file existence when cross compiling
../../lib/autoconf/general.m4:2777: AC_CHECK_FILE is expanded from...
```

Then that's ok for now.

If you get this error:

```sh
checking whether the C++ compiler works... no
```

Then install a C++ compiler:

```
sudo yum install gcc-c++
```

If you get this error:

```sh
checking for SSL support (openssl)... configure: openssl disabled
```

Then install OpenSSL development:

```sh
sudo yum install openssl-devel
```

If you get this error:

```sh
checking for flex... no
```

Then install flex:

```sh
sudo yum install flex
```

Retry as needed.


## Make

Run:

```sh
make
```

If you get this error:

```sh
libtool: Version mismatch error.  This is libtool 2.4.2, but the
libtool: definition of this LT_INIT comes from libtool 2.4.6.
```

Then reconfigure:

```sh
autoreconf --force --install
./configure
make
```


## Install

Run:

```sh
sudo make install
```
