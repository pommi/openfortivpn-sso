# openfortivpn SSO

Inspired by [fuckForticlient](https://github.com/nonamed01/fuckForticlient/), openfortivpn-sso spawns a microsoft-edge browser to get an `SVPNCOOKIE` after a successful SSO login. The `SVPNCOOKIE` is obtained from the browser cookie database and passed along to openfortivpn to connect to the VPN endpoint.

# Why Microsoft Edge?

When your company enables Conditional Access in Microsoft Entra ID, [microsoft-edge is the only supported browser on Linux](https://learn.microsoft.com/en-us/entra/identity/conditional-access/concept-conditional-access-conditions#supported-browsers).

# Prerequisites

## Sudo access to openfortivpn

Make sure that you are allowed to execute `sudo /usr/bin/openfortivpn`

## Install python dependencies

```
$ virtualenv -p python3 .env3
$ pip install -r requirements.txt
```

# Usage

```
$ . .env3/bin/activate
$ ./openfortivpn-sso --help
usage: openfortivpn-sso [-h] --server SERVER [--debug]

Obtains SVPNCOOKIE from browser cookie database and uses that with OpenFortiVPN

options:
  -h, --help            show this help message and exit
  --server SERVER, -S SERVER
                        Server Hostname
  --debug, -d           Enable debugging
```
