# AlaKazaam :warning: WIP :warning:

:books: Reti Peer To Peer - Università degli Studi di Ferrara :books:

A peer-to-peer server based on Kazaa's approach:

## Usage
```shell
python3 AlaKazaam.py
```

**_Note:_** Python 3.6 or above is required

### Peer's supported commands:
[xxxB] = the parameter length in bytes
 
```shell
# Search a Supernode
SUPE[4B].Pktid[16B].IPP2P[55B].PP2P[5B].TTL[2B]
# Response will be
ASUP[4B].Pktid[16B].IPP2P[55B].PP2P[5B]

# Login
LOGI[4B].IPP2P[55B].PP2P[5B]
# Response will be
ALGI[4B].SessionID[16B]

# Add a file
ADFF[4B].SessionID[16B].Filemd5[32B].Filename[100B]
# Response will be
DEFF[4B].SessionID[16B].Filemd5[32B]

# Logout
LOGO[4B].SessionID[16B]
# Response will be
ALGO[4B].\#delete[3B]

# Search a file
QUER[4B].Pktid[16B].IPP2P[55B].PP2P[5B].TTL[2B].Ricerca[20B]
# Response will be
AQUE[4B].Pktid[16B].IPP2P[55B].PP2P[5B].Filemd5[32B].Filename[100B]

# Choose a file among the supernodes
FIND[4B].SessionID[16B].Ricerca[20B]
# Response will be
AFIN[4B].\#idmd5[3B].{Filemd5_i[32B].Filename_i[100B].\#copy_i[3B].{IPP2P_i_j[55B].PP2P_i_j[5B]}(j=1..\#copy_i)}(i=1..\#idmd5)

# Retrieve a file
RETR[4B].Filemd5[16B]
# Response will be
ARET[4B].\#chunk[6B].{Lenchunk_i[5B].data[LB]}(i=1..\#chunk)
```

## Authors :rocket:
* [Federico Frigo](https://github.com/xBlue0)
* [Niccolò Fontana](https://github.com/NicFontana)
* [Giovanni Fiorini](https://github.com/GiovanniFiorini)
* [Marco Rambaldi](https://github.com/jhonrambo93)

Enjoy :sunglasses:
