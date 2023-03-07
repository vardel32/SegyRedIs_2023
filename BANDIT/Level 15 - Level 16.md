# Bandit Level 15 → Level 16
#Bandit #OverTheWire 
## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**
## Solución

Mediante SSL se conecta al puerto 30001, se le proporciona la contraseña del nivel actual y obtenemos la contraseña del siguiente nivel

```bash
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 21 22:03:56 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 21 22:03:56 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 21 22:02:56 2023 GMT; NotAfter: Feb 21 22:03:56 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEF3vcjDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwMjIxMjIwMjU2WhcNMjMwMjIxMjIwMzU2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCg
1elREdWTbtCZNl7KNMjleNrcG71f9lZhjAfM4x+TDwlPpT+Q9O3V6J687fJdMH85
xfUwcZG0XFCeN1nxnmQadGF/ZHEt0laWmCQfo5LogzgGFcaZWC1a6XZ5ZKv7SRDt
tvPK/CTKwOJD5ZJVEXEk9R8YQ/VbKwZMDc43WD/HKypvBv7fZVbJkKYY75LOby86
7gux29Emhntj5pZyYagYbmonnAiw6447bGTC1d6jilGPhXMzckTI57WGeNdp4ppL
3pXSVDLOU2XJ8Um/L2VIgGTsUk5CwrtzVxyt6I5sKavUhsNGlzqvHI/McgbsnHi8
3LDg9k/Co8F21eZFooVlAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBz
lgp6XhMshglRxhxHRg1xHkVYSFSBaS5Adq5OIoE/oetyedTiO2B9MLmNZ9Juu/WK
/+WZFmNdzQ6Iw5ueBz/rmY+DvzTjjd4CPPqeilG5mngceR5nliM9mXkpQlmm3T1a
8JuBrDugrN9BP4IeBTER0pgQcQvsRATrv/SAVFVBhTSvOKFhoYNEdBzaqxclEjD6
bl3UkzNag/S3iLuv24xoQkMmlFC2afaswkG/cQ4p3BuapuZORjbohUOXS24QDl0z
A2RDFNizi42ZVJ8ZW1qbURZ4n/VbIAi7vRHldPKjC8hYAcdvUekB0schBlc1J06Z
phGCgzTVUzJu9yz8uKzO
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 0CEA6DBA90DAC3E1A0313940C467134295E2CBDF83E48BBB686A8D8587CA59A7
    Session-ID-ctx: 
    Resumption PSK: 1678F5E8A0F3B98A5DC93B9B2635604C134EC6DAD3B0AD0C6E90A9275C947B4F0462F8B4B4D0FF6BE30781368FB109F8
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - a5 3d 92 1f d1 78 36 48-bb a6 da 4d 19 13 ee a7   .=...x6H...M....
    0010 - 6f b6 bc 36 a5 4c e2 56-e6 80 31 8a 50 45 12 9e   o..6.L.V..1.PE..
    0020 - c0 58 7f 23 bd 49 fd 26-9d 09 4f e2 00 51 22 29   .X.#.I.&..O..Q")
    0030 - 11 dd 43 c1 e0 53 f0 ab-ed 14 e3 56 22 54 94 2d   ..C..S.....V"T.-
    0040 - 00 1f 06 42 36 fc 34 09-1e 11 e5 e8 e4 fd f4 76   ...B6.4........v
    0050 - 9c 6d ba 35 fe a1 b8 ec-c6 7e cd 43 39 25 df a7   .m.5.....~.C9%..
    0060 - 7c 19 ad d4 e7 9d e2 1d-b2 7f f6 a5 26 d5 49 bf   |...........&.I.
    0070 - be 00 e2 ef e7 c2 14 a0-3f 0b 9b d1 0e e8 f0 fe   ........?.......
    0080 - 91 00 b1 e3 f6 de 9d be-b6 f7 c8 7c 55 36 a1 e3   ...........|U6..
    0090 - 43 2e b3 f4 2e db 99 1e-dc 45 33 ed d9 27 61 49   C........E3..'aI
    00a0 - 57 77 a8 5e 70 2a a0 92-aa a0 1e 80 60 9b 12 a2   Ww.^p*......`...
    00b0 - 6f 3f 17 4a cd f4 5f 57-e2 b6 ac 26 1c b8 df 73   o?.J.._W...&...s
    00c0 - 7c e9 13 2e 88 8f 36 30-86 23 18 53 df 30 ee dd   |.....60.#.S.0..

    Start Time: 1677178312
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: C56E4F89F64AA29D2DC3213D8F6244DEE6073662BE3EDE4F56D16B09C1733F48
    Session-ID-ctx: 
    Resumption PSK: C36E284EA48C7A731CFDA672967AF82D3F8AE19A632A07898CFCE0387A568A057137A7B394A098F2E709895A99146276
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - a5 3d 92 1f d1 78 36 48-bb a6 da 4d 19 13 ee a7   .=...x6H...M....
    0010 - c8 bf d7 10 8a 66 e9 8e-5e 33 e5 da 05 3a 6f 24   .....f..^3...:o$
    0020 - 9e ae ca b7 f7 94 89 28-8b 25 b8 6e 0f 4b 67 a1   .......(.%.n.Kg.
    0030 - da 6b 6f 39 31 dd 78 c2-2a fb 3b 29 c2 18 d5 8b   .ko91.x.*.;)....
    0040 - 41 23 b8 38 1c 00 67 b0-0e 64 85 2f cb de bf aa   A#.8..g..d./....
    0050 - ec ad c6 ef da 5e f9 3e-f9 1c 6f 0f 73 f4 e1 a9   .....^.>..o.s...
    0060 - 45 d9 2f e0 e8 3f 99 bc-20 94 0b f3 35 ff 7d aa   E./..?.. ...5.}.
    0070 - b1 95 ee 10 88 2b f0 79-0c d7 cd 62 57 fd f3 04   .....+.y...bW...
    0080 - 63 8f 72 42 5c c3 c3 b7-05 f2 05 ce f1 f3 e5 84   c.rB\...........
    0090 - 27 02 4d 56 d7 d2 ff 25-28 c8 ab e9 7f 32 e2 35   '.MV...%(....2.5
    00a0 - e7 ff c3 c9 03 45 95 08-f3 cb 7f 44 8e 08 38 7f   .....E.....D..8.
    00b0 - 10 c6 55 e8 09 65 48 db-c9 56 3f 3c a9 09 ae 93   ..U..eH..V?<....
    00c0 - 42 08 de a6 77 0a 32 1b-84 fe 17 26 d7 71 7d ed   B...w.2....&.q}.

    Start Time: 1677178312
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed

```

===JQttfApK4SeyHwDlI9SXGR50qclOAil1===

## Notas adicionales

## Referencias