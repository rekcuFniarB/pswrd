pswrd
=====

`pswrd` is a simple password management util. It doesn't store passwords anywhere, generating output on the fly.

Usage:
------

    pswrd -simple 'any string'

Simple mode. Generate password based on input string. Ommiting 'any string' will prompt for input. Example:

    pswrd -simple 'https://github.com/username'

Output:

    cNq3nZfjC5rNFl2ri6RN

You can also supply a file instead of a string:

    pswrd -file ~/picture.png

Calling without `-simple` arg will run in advanced mode prompting for master password, resource and password version. These info may be passed in args `-password`, `-uri` and `-version` accordingly. "Resource" is usually an URI of a resource, requested password is for. "Version" is password version. Default value is "1", increase it when you want make new password for requested resource.

Example:

    pswrd -password 'my master password' -uri 'https://www.facebook.com/username' -version 2

Output:

    V5YVTe8Au7oeDn2pVcCq

Or same in interactive mode:

    user@computer:/tmp $ pswrd
    Enter master password: my master password
    Enter resource this password is for (usually URI): https://www.facebook.com/username
    Enter password version (default: 1): 2
    
    V5YVTe8Au7oeDn2pVcCq

Note that `-file` doesn't support master password and version.

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
