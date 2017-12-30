## Overview
A simple shell script that creates OpenVPN compatible tunnel profiles in the unified file format. Tested on:
* Linux OpenVPN version 2.4.4
* iOS version 1.1.1 build 212 of OpenVPN Connect
* Android version 0.6.73 of OpenVPN for Android

## Usage
Invoke the script with 5 tokens and the profile is outputted to stdout.
  1. Server Fully Qualified Domain Name of the OpenVPN server (or IP address).
  2. Full path to the CA cert.
  3. Full path to the client cert.
  4. Full path to the client private key.
  5. Full path to the server TLS shared secret key.
  6. Optionally define a port number (defaults to 1194 if left blank).
  7. Optionally define a protocol (defaults to udp if left blank).

### Example (run as root) using all 7 augments to setup a profile working port 443 using TCP
```
CLIENT=foo

./ovpngen nipple.titty.org \
   /etc/openvpn/server/ca.crt \
   /etc/easy-rsa/pki/signed/$CLIENT.crt \
   /etc/easy-rsa/pki/private/$CLIENT.key \
   /etc/openvpn/server/ta.key \
	 443 \
	 tcp > $CLIENT.ovpn
```

The resulting foo.ovpn can be edited if desired. Pay attention to the commented lines!

### Credit
Majority of the credit goes to the script's original author, [trovao](https://github.com/trovao).  His version can be found [here](https://gist.github.com/trovao/18e428b5a758df24455b).
