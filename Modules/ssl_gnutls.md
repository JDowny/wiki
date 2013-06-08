title: Modules &raquo; m_ssl_gnutls
layout: default
---

## Description

Allows you to specify ports to accept clients using SSLv3. See [Secure_Sockets_Layer](null) for information about SSL in 
general; this page addresses issues specific to the GnuTLS module. 

## Configuration Tags

### Configuration of `<bind>`

Add `ssl="gnutls"` to a `<bind>` tag to enable SSL on that port, i.e.:

`<bind address="" port="6667" type="clients" ssl="gnutls">`

or

`<bind address="" port="6666" type="servers" ssl="gnutls">`

You may use SSL on a port with a type of `clients` or of type `servers`. 
You can also have SSL on port `A` on address `X` and plaintext on port `A` on another address `Z`.

i.e. `1.2.3.4` `6697` using ssl and `1.2.3.5` `6697` using plaintext.

### Configuration of the GNUTLS module

Example:
`<gnutls cafile="ca.pem" crlfile="crl.pem" certfile="cert.pem" keyfile="key.pem" dh_bits="1024" certcount="4">`

`<gnutls:cafile>` 

The CA file to use, defaults to `ca.pem`

`<gnutls:crlfile>`

The CRL file to use, defaults to `crl.pem`

`<gnutls:certfile>`

The certificate file, defaults to `cert.pem`

`<gnutls:keyfile>`

The private key file, defaults to `key.pem`

`<gnutls:certcount>`

The number of certificates in the certificate file (certificate chain); required if you get an error about memory 
buffers.

`<gnutls:dh_bits>`

The number of bits to use for DH (Diffie Hellman) parameter generation, defaults to 1024. May be 768, 1024, 2048, 3072 
or 4096.

`<gnutls:hash>`

The hash to use for fingerprints. Defaults to MD5; you may also specify SHA1. 

(As usual, relative paths in the `<gnutls>` tag are treated as relative to the inspircd config directory, absolute ones 
are treated as absolute.)

## Commands

`/REHASH SSL`

This command will cause all the certificates to be reloaded and Diffie Hellman parameters regenerated, <bind> tags are 
also re-read.

`/STARTTLS`

In 1.2 of InspIRCd and onwards, clients may send `/STARTTLS` before client registration to switch a plaintext socket to 
GNUTLS mode. After this point, the server expects the TLS handshake. No further plaintext should be sent and there is 
no way to revert back to plaintext after this point.

For more information on `/STARTTLS` see the [STARTTLS Documentation page](null). Note that this command only works on 
plaintext ports - it will give an error on SSL ports, which start their handshake as soon as the connection is begun. 

## User Modes

This module implements no user modes.

## SNOMASK

This module implements no server notice masks.

## Channel Modes



## Extbans

This module implements no extended bans.

## Special Notes

**Important**: The GnuTLS module **can** be unloaded with the `/UNLOADMODULE` command, *however* this will result in 
*all* users connecting via the module to be killed off the network with the reason `SSL module unloading`:

`(23-14:53:46)  -» (Om)(~om@NetAdmin.easnet.net) has quit (SSL module unloading)`

**Beware of unloading this module!**

### OpenSSL vs. GNUTLS

GnuTLS has been benchmarked against OpenSSL and GnuTLS is significantly faster, InspIRCd has both GnuTLS and OpenSSL 
support but we recommend this GnuTLS version over the OpenSSL one! It should outperform it and due to GnuTLS's nicer 
API the module itself is smaller and neater than the OpenSSL module.

**This is the recommended SSL module!**

### Installation

This module requires libgnutls to work, currently it has been tested with the 1.2, 1.3, 2.2, 2.4 and 2.6 series of 
libgnutls. You must have this and the appropriate header files in order to build the module.

Once the module is compiled you need to generate a private key and an ssl certificate, GnuTLS supplies a tool called 
`certtool` which makes this process fairly easy. Just run these two commands and move the output .pem files to 
wherever you configured.

`certtool --generate-privkey --bits 2048 --outfile key.pem`
`certtool --generate-self-signed --load-privkey key.pem --outfile cert.pem`

Of course you may want to vary this to use a private key you already have, or to get the certificate signed by someone 
else, in which case use `man certtool` to learn more.

If your key takes a long time to generate and you also have OpenSSL installed you can generate a key and certificate 
with the following command:

`openssl req -x509 -nodes -newkey rsa:2048 -keyout key.pem -out cert.pem`

Also it will aid in the key generation if you cause device activity during the generation, this helps supply random data.

If you are using certificates that need chaining, please note that unlike openssl, GnuTLS expects the server certificate 
to contain both the server certificate AND the certificate chain (simply concatenating the files will work). There is 
no separate setting to the certificate chain. Note that the order is `server` > `intermediate` > `root`!

Example concatenation on Debian GNU/Linux:

`cat cert.pem > chain.pem` This places the server certificate first in the file.

`cat intermediate.pem >> chain.pem` Next we add the intermediary certificate.

`cat root.pem >> chain.pem` Last we add the root certificate of the chain.


#### Installation of GNUTLS to your home directory

In the instance where you do not have root access to the place where you will be running InspIRCd, and you still want 
to use GnuTLS, you must install it to your home directory.

InspIRCd is designed in such a way that if you do this, it will work, so long as the GnuTLS binaries are in the PATH. 
Usually, most Linux and BSD distributions insert `/home/username/bin` or `~/bin` into the path, so by copying `certtool` 
and `libgnutls-config` to this directory, you can make GnuTLS function as expected with InspIRCd. So long as it can 
execute these binaries, it can successfully compile, and detect the libraries it needs.
Package Systems

Some distro's have decided to package GnuTLS in a unique manner. You may need to check to make sure you install all 
the required packages as it may be more than one. `pkg-config` is also required for GnuTLS detection as of 
InspIRCd 1.2rc4, InspIRCd 1.1.23 and onwards. 

Example package manager commands for various GNU/Linux distributions:

Debian 6/Squeeze

`apt-get install libgnutls26 libgnutls-dev gnutls-bin pkg-config`

Debian 7/Wheeyz

`apt-get install libgnutls28 libgnutls-dev gnutls-bin pkg-config`

Ubuntu 8.04 LTS "Hardy Heron" to 11.10 "Oneiric Ocelot"

`apt-get install gnutls-bin gnutls-dev pkg-config`

Fedora 7

`yum install gnutls gnutls-devel gnutls-utils pkgconfig`

**Please check with your Distro's documentation and ensure all components are loaded before reporting a fault.**
