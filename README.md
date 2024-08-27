# xpass extension for PHP

This extension provides password hashing algorithms used in Linux distributions.

* **sha512** (`$6$`) provided for legacy as used on some old distributions (ex: RHEL-8)
* **yescrypt** (`$y$`) used on modern distributions

----

# Sources

* Official git repository: https://git.remirepo.net/cgit/tools/php-xpass.git/
* Mirror on github for contributors: https://github.com/remicollet/php-xpass

----

# Build

You need the Extended crypt library development files (libxcrypt-devel)

From the sources tree

    $ phpize
    $ ./configure --enable-xpass
    $ make
    $ make test

----

# Usage

## password hashing

    $ php -a
    php > var_dump($hash = password_hash("secret", PASSWORD_YESCRYPT));
    string(73) "$y$j9T$X9Va6i3zHjyKGJAskYZPv.$i1m/WR1C6/tqhB7IdOsi9Ar1JF4Qr38vBx104ao1OS5"
    php > var_dump(password_verify("secret", $hash));
    bool(true)

----

# LICENSE

Author: Remi Collet

This extension is licensed under [The PHP License, version 3.01](http://www.php.net/license/3_01.txt)

-----

# History

Created on user request
