pswrd
=====

`pswrd` is a simple password generating util.

Usage:
------

    pswrd 'any string'

Above command generates password for string "any string". Example:

    pswrd 'https://github.com/rekcuFniarB'

Output:

    m2MOQDCpeH1U8YGP3rKWHw

You can also supply a file instead of string:

    pswrd -f picture.png

Install:
--------

Just copy the script to any path you will run it from (`/usr/local/bin` for example).

### Requirements:

* `md5sum`
* `head`
* `sed`
* `xxd`
* `base64`
* `dd`
