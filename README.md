OpenSSL
================

This is a fork of the official OpenSSL github repository at https://github.com/openssl/openssl.git

You're looking at the 1.0.2-chacha branch, which aligns with the OpenSSL_1_0_2-stable branch.

The main reason of the fork is to include ChaCha20, Poly1305 and experimental/insecure ciphers, and to add some extra features to s_client. It should compile 'as least as good' as the official OpenSSL_1_0_2-stable branch.

* Added ChaCha20 and Poly1305 ciphers (backported from the upstream 1.0.2-aead branch)
* Enabled TLS1_ALLOW_EXPERIMENTAL_CIPHERSUITE
* Enabled SSLv2 cipher NULL_WITH_MD5 v3
* Minor changes to Makefiles to simplify building using the mingw / mingw64 platform on Windows
* Minor additions to s_client (-proxy)

This branch can be compiled directly without any modification (especially on Windows using mingw / mingw64).

The latest binary Windows 64-bit builds of these branches can be found at http://onwebsecurity.com/cryptography/openssl
The version string of thses binaries includes the branch name and commit hash.

Please see the official OpenSSL repository for all relevant license / copyright info. This repository is merely a fork of their great work with some minimal additions and changes.


Supported ciphers:
ECDHE-ECDSA-CHACHA20-POLY1305 TLSv1.2 Kx=ECDH     Au=ECDSA Enc=ChaCha20-Poly1305 Mac=AEAD
ECDHE-RSA-CHACHA20-POLY1305 TLSv1.2 Kx=ECDH     Au=RSA  Enc=ChaCha20-Poly1305 Mac=AEAD
DHE-RSA-CHACHA20-POLY1305 TLSv1.2 Kx=DH       Au=RSA  Enc=ChaCha20-Poly1305 Mac=AEAD
ECDHE-RSA-AES256-GCM-SHA384 TLSv1.2 Kx=ECDH     Au=RSA  Enc=AESGCM(256) Mac=AEAD
ECDHE-ECDSA-AES256-GCM-SHA384 TLSv1.2 Kx=ECDH     Au=ECDSA Enc=AESGCM(256) Mac=AEAD
ECDHE-RSA-AES256-SHA384 TLSv1.2 Kx=ECDH     Au=RSA  Enc=AES(256)  Mac=SHA384
ECDHE-ECDSA-AES256-SHA384 TLSv1.2 Kx=ECDH     Au=ECDSA Enc=AES(256)  Mac=SHA384
ECDHE-RSA-AES256-SHA    SSLv3 Kx=ECDH     Au=RSA  Enc=AES(256)  Mac=SHA1
ECDHE-ECDSA-AES256-SHA  SSLv3 Kx=ECDH     Au=ECDSA Enc=AES(256)  Mac=SHA1
SRP-DSS-AES-256-CBC-SHA SSLv3 Kx=SRP      Au=DSS  Enc=AES(256)  Mac=SHA1
SRP-RSA-AES-256-CBC-SHA SSLv3 Kx=SRP      Au=RSA  Enc=AES(256)  Mac=SHA1
SRP-AES-256-CBC-SHA     SSLv3 Kx=SRP      Au=SRP  Enc=AES(256)  Mac=SHA1
DH-DSS-AES256-GCM-SHA384 TLSv1.2 Kx=DH/DSS   Au=DH   Enc=AESGCM(256) Mac=AEAD
DHE-DSS-AES256-GCM-SHA384 TLSv1.2 Kx=DH       Au=DSS  Enc=AESGCM(256) Mac=AEAD
DH-RSA-AES256-GCM-SHA384 TLSv1.2 Kx=DH/RSA   Au=DH   Enc=AESGCM(256) Mac=AEAD
DHE-RSA-AES256-GCM-SHA384 TLSv1.2 Kx=DH       Au=RSA  Enc=AESGCM(256) Mac=AEAD
DHE-RSA-AES256-SHA256   TLSv1.2 Kx=DH       Au=RSA  Enc=AES(256)  Mac=SHA256
DHE-DSS-AES256-SHA256   TLSv1.2 Kx=DH       Au=DSS  Enc=AES(256)  Mac=SHA256
DH-RSA-AES256-SHA256    TLSv1.2 Kx=DH/RSA   Au=DH   Enc=AES(256)  Mac=SHA256
DH-DSS-AES256-SHA256    TLSv1.2 Kx=DH/DSS   Au=DH   Enc=AES(256)  Mac=SHA256
DHE-RSA-AES256-SHA      SSLv3 Kx=DH       Au=RSA  Enc=AES(256)  Mac=SHA1
DHE-DSS-AES256-SHA      SSLv3 Kx=DH       Au=DSS  Enc=AES(256)  Mac=SHA1
DH-RSA-AES256-SHA       SSLv3 Kx=DH/RSA   Au=DH   Enc=AES(256)  Mac=SHA1
DH-DSS-AES256-SHA       SSLv3 Kx=DH/DSS   Au=DH   Enc=AES(256)  Mac=SHA1
DHE-RSA-CAMELLIA256-SHA SSLv3 Kx=DH       Au=RSA  Enc=Camellia(256) Mac=SHA1
DHE-DSS-CAMELLIA256-SHA SSLv3 Kx=DH       Au=DSS  Enc=Camellia(256) Mac=SHA1
DH-RSA-CAMELLIA256-SHA  SSLv3 Kx=DH/RSA   Au=DH   Enc=Camellia(256) Mac=SHA1
DH-DSS-CAMELLIA256-SHA  SSLv3 Kx=DH/DSS   Au=DH   Enc=Camellia(256) Mac=SHA1
AECDH-AES256-SHA        SSLv3 Kx=ECDH     Au=None Enc=AES(256)  Mac=SHA1
ADH-AES256-GCM-SHA384   TLSv1.2 Kx=DH       Au=None Enc=AESGCM(256) Mac=AEAD
ADH-AES256-SHA256       TLSv1.2 Kx=DH       Au=None Enc=AES(256)  Mac=SHA256
ADH-AES256-SHA          SSLv3 Kx=DH       Au=None Enc=AES(256)  Mac=SHA1
ADH-CAMELLIA256-SHA     SSLv3 Kx=DH       Au=None Enc=Camellia(256) Mac=SHA1
ECDH-RSA-AES256-GCM-SHA384 TLSv1.2 Kx=ECDH/RSA Au=ECDH Enc=AESGCM(256) Mac=AEAD
ECDH-ECDSA-AES256-GCM-SHA384 TLSv1.2 Kx=ECDH/ECDSA Au=ECDH Enc=AESGCM(256) Mac=AEAD
ECDH-RSA-AES256-SHA384  TLSv1.2 Kx=ECDH/RSA Au=ECDH Enc=AES(256)  Mac=SHA384
ECDH-ECDSA-AES256-SHA384 TLSv1.2 Kx=ECDH/ECDSA Au=ECDH Enc=AES(256)  Mac=SHA384
ECDH-RSA-AES256-SHA     SSLv3 Kx=ECDH/RSA Au=ECDH Enc=AES(256)  Mac=SHA1
ECDH-ECDSA-AES256-SHA   SSLv3 Kx=ECDH/ECDSA Au=ECDH Enc=AES(256)  Mac=SHA1
AES256-GCM-SHA384       TLSv1.2 Kx=RSA      Au=RSA  Enc=AESGCM(256) Mac=AEAD
AES256-SHA256           TLSv1.2 Kx=RSA      Au=RSA  Enc=AES(256)  Mac=SHA256
AES256-SHA              SSLv3 Kx=RSA      Au=RSA  Enc=AES(256)  Mac=SHA1
CAMELLIA256-SHA         SSLv3 Kx=RSA      Au=RSA  Enc=Camellia(256) Mac=SHA1
PSK-AES256-CBC-SHA      SSLv3 Kx=PSK      Au=PSK  Enc=AES(256)  Mac=SHA1
ECDHE-RSA-AES128-GCM-SHA256 TLSv1.2 Kx=ECDH     Au=RSA  Enc=AESGCM(128) Mac=AEAD
ECDHE-ECDSA-AES128-GCM-SHA256 TLSv1.2 Kx=ECDH     Au=ECDSA Enc=AESGCM(128) Mac=AEAD
ECDHE-RSA-AES128-SHA256 TLSv1.2 Kx=ECDH     Au=RSA  Enc=AES(128)  Mac=SHA256
ECDHE-ECDSA-AES128-SHA256 TLSv1.2 Kx=ECDH     Au=ECDSA Enc=AES(128)  Mac=SHA256
ECDHE-RSA-AES128-SHA    SSLv3 Kx=ECDH     Au=RSA  Enc=AES(128)  Mac=SHA1
ECDHE-ECDSA-AES128-SHA  SSLv3 Kx=ECDH     Au=ECDSA Enc=AES(128)  Mac=SHA1
SRP-DSS-AES-128-CBC-SHA SSLv3 Kx=SRP      Au=DSS  Enc=AES(128)  Mac=SHA1
SRP-RSA-AES-128-CBC-SHA SSLv3 Kx=SRP      Au=RSA  Enc=AES(128)  Mac=SHA1
SRP-AES-128-CBC-SHA     SSLv3 Kx=SRP      Au=SRP  Enc=AES(128)  Mac=SHA1
DH-DSS-AES128-GCM-SHA256 TLSv1.2 Kx=DH/DSS   Au=DH   Enc=AESGCM(128) Mac=AEAD
DHE-DSS-AES128-GCM-SHA256 TLSv1.2 Kx=DH       Au=DSS  Enc=AESGCM(128) Mac=AEAD
DH-RSA-AES128-GCM-SHA256 TLSv1.2 Kx=DH/RSA   Au=DH   Enc=AESGCM(128) Mac=AEAD
DHE-RSA-AES128-GCM-SHA256 TLSv1.2 Kx=DH       Au=RSA  Enc=AESGCM(128) Mac=AEAD
DHE-RSA-AES128-SHA256   TLSv1.2 Kx=DH       Au=RSA  Enc=AES(128)  Mac=SHA256
DHE-DSS-AES128-SHA256   TLSv1.2 Kx=DH       Au=DSS  Enc=AES(128)  Mac=SHA256
DH-RSA-AES128-SHA256    TLSv1.2 Kx=DH/RSA   Au=DH   Enc=AES(128)  Mac=SHA256
DH-DSS-AES128-SHA256    TLSv1.2 Kx=DH/DSS   Au=DH   Enc=AES(128)  Mac=SHA256
DHE-RSA-AES128-SHA      SSLv3 Kx=DH       Au=RSA  Enc=AES(128)  Mac=SHA1
DHE-DSS-AES128-SHA      SSLv3 Kx=DH       Au=DSS  Enc=AES(128)  Mac=SHA1
DH-RSA-AES128-SHA       SSLv3 Kx=DH/RSA   Au=DH   Enc=AES(128)  Mac=SHA1
DH-DSS-AES128-SHA       SSLv3 Kx=DH/DSS   Au=DH   Enc=AES(128)  Mac=SHA1
DHE-RSA-SEED-SHA        SSLv3 Kx=DH       Au=RSA  Enc=SEED(128) Mac=SHA1
DHE-DSS-SEED-SHA        SSLv3 Kx=DH       Au=DSS  Enc=SEED(128) Mac=SHA1
DH-RSA-SEED-SHA         SSLv3 Kx=DH/RSA   Au=DH   Enc=SEED(128) Mac=SHA1
DH-DSS-SEED-SHA         SSLv3 Kx=DH/DSS   Au=DH   Enc=SEED(128) Mac=SHA1
DHE-RSA-CAMELLIA128-SHA SSLv3 Kx=DH       Au=RSA  Enc=Camellia(128) Mac=SHA1
DHE-DSS-CAMELLIA128-SHA SSLv3 Kx=DH       Au=DSS  Enc=Camellia(128) Mac=SHA1
DH-RSA-CAMELLIA128-SHA  SSLv3 Kx=DH/RSA   Au=DH   Enc=Camellia(128) Mac=SHA1
DH-DSS-CAMELLIA128-SHA  SSLv3 Kx=DH/DSS   Au=DH   Enc=Camellia(128) Mac=SHA1
AECDH-AES128-SHA        SSLv3 Kx=ECDH     Au=None Enc=AES(128)  Mac=SHA1
ADH-AES128-GCM-SHA256   TLSv1.2 Kx=DH       Au=None Enc=AESGCM(128) Mac=AEAD
ADH-AES128-SHA256       TLSv1.2 Kx=DH       Au=None Enc=AES(128)  Mac=SHA256
ADH-AES128-SHA          SSLv3 Kx=DH       Au=None Enc=AES(128)  Mac=SHA1
ADH-SEED-SHA            SSLv3 Kx=DH       Au=None Enc=SEED(128) Mac=SHA1
ADH-CAMELLIA128-SHA     SSLv3 Kx=DH       Au=None Enc=Camellia(128) Mac=SHA1
ECDH-RSA-AES128-GCM-SHA256 TLSv1.2 Kx=ECDH/RSA Au=ECDH Enc=AESGCM(128) Mac=AEAD
ECDH-ECDSA-AES128-GCM-SHA256 TLSv1.2 Kx=ECDH/ECDSA Au=ECDH Enc=AESGCM(128) Mac=AEAD
ECDH-RSA-AES128-SHA256  TLSv1.2 Kx=ECDH/RSA Au=ECDH Enc=AES(128)  Mac=SHA256
ECDH-ECDSA-AES128-SHA256 TLSv1.2 Kx=ECDH/ECDSA Au=ECDH Enc=AES(128)  Mac=SHA256
ECDH-RSA-AES128-SHA     SSLv3 Kx=ECDH/RSA Au=ECDH Enc=AES(128)  Mac=SHA1
ECDH-ECDSA-AES128-SHA   SSLv3 Kx=ECDH/ECDSA Au=ECDH Enc=AES(128)  Mac=SHA1
AES128-GCM-SHA256       TLSv1.2 Kx=RSA      Au=RSA  Enc=AESGCM(128) Mac=AEAD
AES128-SHA256           TLSv1.2 Kx=RSA      Au=RSA  Enc=AES(128)  Mac=SHA256
AES128-SHA              SSLv3 Kx=RSA      Au=RSA  Enc=AES(128)  Mac=SHA1
SEED-SHA                SSLv3 Kx=RSA      Au=RSA  Enc=SEED(128) Mac=SHA1
CAMELLIA128-SHA         SSLv3 Kx=RSA      Au=RSA  Enc=Camellia(128) Mac=SHA1
IDEA-CBC-SHA            SSLv3 Kx=RSA      Au=RSA  Enc=IDEA(128) Mac=SHA1
IDEA-CBC-MD5            SSLv2 Kx=RSA      Au=RSA  Enc=IDEA(128) Mac=MD5
RC2-CBC-MD5             SSLv2 Kx=RSA      Au=RSA  Enc=RC2(128)  Mac=MD5
PSK-AES128-CBC-SHA      SSLv3 Kx=PSK      Au=PSK  Enc=AES(128)  Mac=SHA1
ECDHE-RSA-RC4-SHA       SSLv3 Kx=ECDH     Au=RSA  Enc=RC4(128)  Mac=SHA1
ECDHE-ECDSA-RC4-SHA     SSLv3 Kx=ECDH     Au=ECDSA Enc=RC4(128)  Mac=SHA1
DHE-DSS-RC4-SHA         SSLv3 Kx=DH       Au=DSS  Enc=RC4(128)  Mac=SHA1
AECDH-RC4-SHA           SSLv3 Kx=ECDH     Au=None Enc=RC4(128)  Mac=SHA1
ADH-RC4-MD5             SSLv3 Kx=DH       Au=None Enc=RC4(128)  Mac=MD5
ECDH-RSA-RC4-SHA        SSLv3 Kx=ECDH/RSA Au=ECDH Enc=RC4(128)  Mac=SHA1
ECDH-ECDSA-RC4-SHA      SSLv3 Kx=ECDH/ECDSA Au=ECDH Enc=RC4(128)  Mac=SHA1
RC4-SHA                 SSLv3 Kx=RSA      Au=RSA  Enc=RC4(128)  Mac=SHA1
RC4-MD5                 SSLv3 Kx=RSA      Au=RSA  Enc=RC4(128)  Mac=MD5
RC4-MD5                 SSLv2 Kx=RSA      Au=RSA  Enc=RC4(128)  Mac=MD5
PSK-RC4-SHA             SSLv3 Kx=PSK      Au=PSK  Enc=RC4(128)  Mac=SHA1
ECDHE-RSA-DES-CBC3-SHA  SSLv3 Kx=ECDH     Au=RSA  Enc=3DES(168) Mac=SHA1
ECDHE-ECDSA-DES-CBC3-SHA SSLv3 Kx=ECDH     Au=ECDSA Enc=3DES(168) Mac=SHA1
SRP-DSS-3DES-EDE-CBC-SHA SSLv3 Kx=SRP      Au=DSS  Enc=3DES(168) Mac=SHA1
SRP-RSA-3DES-EDE-CBC-SHA SSLv3 Kx=SRP      Au=RSA  Enc=3DES(168) Mac=SHA1
SRP-3DES-EDE-CBC-SHA    SSLv3 Kx=SRP      Au=SRP  Enc=3DES(168) Mac=SHA1
EDH-RSA-DES-CBC3-SHA    SSLv3 Kx=DH       Au=RSA  Enc=3DES(168) Mac=SHA1
EDH-DSS-DES-CBC3-SHA    SSLv3 Kx=DH       Au=DSS  Enc=3DES(168) Mac=SHA1
DH-RSA-DES-CBC3-SHA     SSLv3 Kx=DH/RSA   Au=DH   Enc=3DES(168) Mac=SHA1
DH-DSS-DES-CBC3-SHA     SSLv3 Kx=DH/DSS   Au=DH   Enc=3DES(168) Mac=SHA1
AECDH-DES-CBC3-SHA      SSLv3 Kx=ECDH     Au=None Enc=3DES(168) Mac=SHA1
ADH-DES-CBC3-SHA        SSLv3 Kx=DH       Au=None Enc=3DES(168) Mac=SHA1
ECDH-RSA-DES-CBC3-SHA   SSLv3 Kx=ECDH/RSA Au=ECDH Enc=3DES(168) Mac=SHA1
ECDH-ECDSA-DES-CBC3-SHA SSLv3 Kx=ECDH/ECDSA Au=ECDH Enc=3DES(168) Mac=SHA1
DES-CBC3-SHA            SSLv3 Kx=RSA      Au=RSA  Enc=3DES(168) Mac=SHA1
DES-CBC3-MD5            SSLv2 Kx=RSA      Au=RSA  Enc=3DES(168) Mac=MD5
PSK-3DES-EDE-CBC-SHA    SSLv3 Kx=PSK      Au=PSK  Enc=3DES(168) Mac=SHA1
RC4-64-MD5              SSLv2 Kx=RSA      Au=RSA  Enc=RC4(64)   Mac=MD5
EXP1024-DHE-DSS-DES-CBC-SHA SSLv3 Kx=DH(1024) Au=DSS  Enc=DES(56)   Mac=SHA1 export
EDH-RSA-DES-CBC-SHA     SSLv3 Kx=DH       Au=RSA  Enc=DES(56)   Mac=SHA1
EDH-DSS-DES-CBC-SHA     SSLv3 Kx=DH       Au=DSS  Enc=DES(56)   Mac=SHA1
DH-RSA-DES-CBC-SHA      SSLv3 Kx=DH/RSA   Au=DH   Enc=DES(56)   Mac=SHA1
DH-DSS-DES-CBC-SHA      SSLv3 Kx=DH/DSS   Au=DH   Enc=DES(56)   Mac=SHA1
ADH-DES-CBC-SHA         SSLv3 Kx=DH       Au=None Enc=DES(56)   Mac=SHA1
EXP1024-DES-CBC-SHA     SSLv3 Kx=RSA(1024) Au=RSA  Enc=DES(56)   Mac=SHA1 export
DES-CBC-SHA             SSLv3 Kx=RSA      Au=RSA  Enc=DES(56)   Mac=SHA1
DES-CBC-MD5             SSLv2 Kx=RSA      Au=RSA  Enc=DES(56)   Mac=MD5
EXP1024-DHE-DSS-RC4-SHA SSLv3 Kx=DH(1024) Au=DSS  Enc=RC4(56)   Mac=SHA1 export
EXP1024-RC4-SHA         SSLv3 Kx=RSA(1024) Au=RSA  Enc=RC4(56)   Mac=SHA1 export
EXP-EDH-RSA-DES-CBC-SHA SSLv3 Kx=DH(512)  Au=RSA  Enc=DES(40)   Mac=SHA1 export
EXP-EDH-DSS-DES-CBC-SHA SSLv3 Kx=DH(512)  Au=DSS  Enc=DES(40)   Mac=SHA1 export
EXP-DH-RSA-DES-CBC-SHA  SSLv3 Kx=DH/RSA   Au=DH   Enc=DES(40)   Mac=SHA1 export
EXP-DH-DSS-DES-CBC-SHA  SSLv3 Kx=DH/DSS   Au=DH   Enc=DES(40)   Mac=SHA1 export
EXP-ADH-DES-CBC-SHA     SSLv3 Kx=DH(512)  Au=None Enc=DES(40)   Mac=SHA1 export
EXP-DES-CBC-SHA         SSLv3 Kx=RSA(512) Au=RSA  Enc=DES(40)   Mac=SHA1 export
EXP-RC2-CBC-MD5         SSLv3 Kx=RSA(512) Au=RSA  Enc=RC2(40)   Mac=MD5  export
EXP-RC2-CBC-MD5         SSLv2 Kx=RSA(512) Au=RSA  Enc=RC2(40)   Mac=MD5  export
EXP-ADH-RC4-MD5         SSLv3 Kx=DH(512)  Au=None Enc=RC4(40)   Mac=MD5  export
EXP-RC4-MD5             SSLv3 Kx=RSA(512) Au=RSA  Enc=RC4(40)   Mac=MD5  export
EXP-RC4-MD5             SSLv2 Kx=RSA(512) Au=RSA  Enc=RC4(40)   Mac=MD5  export
