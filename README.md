pswrd
=====

`pswrd` is a simple password management util. It doesn't store passwords anywhere, generating output on the fly.

There is also [GUI version with Android support](https://github.com/rekcuFniarB/pswrd.py#readme).

Why this wheel was reinvented? Well, I needed a simple util which doesn't require syncing data between devices.

Usage:
------

Calling without `-simple` arg will run in advanced mode prompting for master password, user name, domain and password version. These info may be passed in args `-password`, `-user`, `-domain` and `-version` accordingly. "Version" is password version. Default value is "1", increase it when you want make new password for requested the same user+domain pair.

Example:

    pswrd -password 'my master password' -user 'username' -domain 'facebook.com' -version 2

Output:

    V5YVTe8Au7oeDn2pVcCq

Or same in interactive mode:

    user@computer:/tmp $ pswrd
    Enter master password:
    Enter user name (default: empty): username
    Enter service name (usually domain name): facebook.com
    Enter password version (default: 1): 2
    
    V5YVTe8Au7oeDn2pVcCq

Output password string will also be placed to the clipboard if `xclip` util is available and `-nc` arg not specified.


### Simple mode ###

There is also simple mode:

    pswrd -simple 'any string'

Simple mode. Generate password based on input string. Ommiting 'any string' will prompt for input. Example:

    pswrd -simple 'https://github.com/username'

Output:

    cNq3nZfjC5rNFl2ri6RN

You can also supply a file instead of a string:

    pswrd -file ~/picture.png

Note that `-file` mode doesn't support master password and version.


#### Other args

`-alnum` allows alphanumeric chars only in output.

`-random` generates random string.

Install:
--------

Just copy the script to any path you will run it from (`/usr/local/bin` for example).

### Requirements:

* `md5sum`
* `head`
* `sed`
* `xxd`
* `base64`
