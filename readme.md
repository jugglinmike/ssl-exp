# SSL Experimentation

## Prerequisites

- VirtualBox
- Vagrant

## Setup

1. Add the following entries to your `hosts` file:

        192.168.101.101	ssl-exp.local
        192.168.101.101	a.ssl-exp.local
        192.168.101.101	b.ssl-exp.local

2. Run `vagrant up`

Requests to the following locations should now be satisfied with simple index
pages (self-signed certificate warnings and all).

- `https://a.ssl-exp.local`
- `https://b.ssl-exp.local`

## Key Generation

The cryptographic keypair included in this project were generated within an
instance of the virtual machine using the following commands:

    openssl req -new -x509 -nodes -out server.crt -keyout server.key
    chmod 600 server.key

## Resources

- http://dracoblue.net/dev/https-nginx-with-self-signed-ssl-certificate/

## License

Copyright (c) 2015 Mike Pennisi  
Licensed under the GNU General Public License, version 3.
