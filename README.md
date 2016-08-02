## Overview
A simple shell script that creates OpenVPN compatible tunnel profiles in the unified file format. Tested on iOS version 1.0.7 build 199 of OpenVPN Connect and likely works with the Android app as well as the official Linux client.

## Usage
Invoke the script with 5 tokens and the profile is outputted to stdout.
  1. Server Fully Qualified Domain Name of the OpenVPN server (or IP address).
  2. Full path to the CA cert.
  3. Full path to the client cert.
  4. Full path to the client private key.
  5. Full path to the server TLS shared secret key.
  6. Optionally define a port number (defaults to 1194 if left blank).
  7. Optionally define a protocol (defaults to udp if left blank).

### Example
```
sudo ./ovpngen titty.nipples.org /etc/easy-rsa/pki/ca.crt /etc/easy-rsa/pki/issued/client.crt /etc/easy-rsa/pki/private/client.key /etc/openvpn/ta.key > myprofile.ovpn
```

The resulting myprofile.ovpn can be edited if desired.

### Credit
Majority of the credit goes to the script's original author, [trovao](https://github.com/trovao).  His version can be found [here](https://gist.github.com/trovao/18e428b5a758df24455b).
