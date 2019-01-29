Build status: [![build_status](https://travis-ci.org/sndr-oss/quickxorhash-c.svg?branch=master)](https://travis-ci.org/sndr-oss/quickxorhash-c)
# quickxorhash

quickxorhash is a C library (libqxh) implementing Microsoft's
QuickXORHash algorithm. It also includes a small command-line utility
that calculates and displays the hash of a file.

## Algorithm

QuickXORHash is a non-cryptographic hash function that XORs the input
bytes in a circular shift pattern, then XORs the least significant
bits of the hash with the input length. The canonical representation
of the resulting hash is a Base64 encoded string, because hexadecimal
is too plebeian.

## Dependencies

* [OpenSSL](https://openssl.org/) or a compatible implementation of libcrypto.

## Uses

The only known usage of this hash is in OneDrive for Business; consumer
OneDrive uses SHA-1 and CRC32 for fingerprinting.

## Ubuntu build and test
```bash
sudo apt-get install libtool automake
cd quickxorhash/
autoreconf -i
./configure
make
./quickxorhash cli.c
5KhRHn59xYIDPsCuvN+xY3TkK+Q=
```
