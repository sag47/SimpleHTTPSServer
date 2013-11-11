# SimpleHTTPSServer

It's like a secure pastebin but for files!  Run this command anywhere and you instantly have secure file sharing (assuming you set up signed certificates before hand) based on the current working directory of the command.  Also be aware that port `8000` will be open for all interfaces so it is assumed you will lock your system down with a firewall and only share to specific IP addresses or IP ranges using a firewall like iptables.

## Prerequisites

In addition to Python 2.6 or Python 2.7 you need to have [pyOpenSSL installed](https://launchpad.net/pyopenssl/)

## Installation

Copy the version of `SimpleHTTPSServer` you want to use to the python modules directory.  e.g.

    cp SimpleHTTPSServer.py /usr/lib/python2.7/SimpleHTTPSServer.py

## Usage

    python -m SimpleHTTPSServer

1. Start the https server by simply running SimpleSecureHTTPServer.py for the desired version of Python (2.6 or 2.7).
2. Visit `https://localhost:8000/` or `https://yourhost.yourdomain.com:8000`

Note: Other versions of python are untested but still may work.

# References

Originally obtained from [active state](http://code.activestate.com/recipes/442473-simple-http-server-supporting-ssl-secure-communica/)

This is a modification of [Python 2.6 SimpleHTTPServer](http://docs.python.org/release/2.6.8/library/simplehttpserver.html) and [Python 2.7 SimpleHTTPServer](http://docs.python.org/library/simplehttpserver.html)

There is a pyOpenSSL bug where it does not work properly with socket in Python 2.7.

* https://bugs.launchpad.net/pyopenssl/+bug/686804
* https://bugs.launchpad.net/pyopenssl/+bug/755852

I wrote a workaround which is applied in the Python 2.7 directory to account for this.  Now we have the best of both worlds and it works with Python 2.7!

