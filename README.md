# The XBR Protocol

[![Docs (on CDN)](https://img.shields.io/badge/docs-cdn-brightgreen.svg?style=flat)](https://xbr.network/docs/index.html) &nbsp; [![Docs (on S3)](https://img.shields.io/badge/docs-s3-brightgreen.svg?style=flat)](https://s3.eu-central-1.amazonaws.com/xbr.foundation/docs/index.html) &nbsp; [![Travis](https://travis-ci.org/xbr/xbr-protocol.svg?branch=master)](https://travis-ci.org/xbr/xbr-protocol) &nbsp; [![Coverage](https://img.shields.io/codecov/c/github/xbr/xbr-protocol/master.svg)](https://codecov.io/github/xbr/xbr-protocol)

This repository contains the XBR smart contracts, with Ethereum as target blockchain, and Solidity as implementation language for the **XBR Protocol**.

Please see the [documentation](https://xbr.network/docs/index.html) for more information.

## XBR Client Library

The XBR Protocol - at its core - is made of the XBR smart contracts, and the
primary artifacts built are the contract ABI files (in ``./build/contracts/*.json``).

Technically, these files are all you need to interact and talk to the XBR
smart contracts.

However, doing it that way (using the raw ABI files and presumably some generic
Ethereum library) is cumbersome and error prone to maintain.

Therefore, we create wrapper libraries for XBR, currently for Python and JavaScript,
that make interaction with XBR contract super easy.

The libraries are available here:

* [XBR client library for Python](<https://pypi.org/project/xbr/>)
* [XBR client library for JavaScript/Browser](<https://xbr.network/lib/xbr.min.js>)
* [XBR client library for JavaScript/NodeJS](<https://www.npmjs.org/package/xbr>)

### XBR Lib for Browser

To use XBR Lib for JavaScript (in a browser Dapp), add a reference to the
latest development version we host:

```html
<script>
    XBR_DEBUG_TOKEN_ADDR = '0x67b5656d60a809915323bf2c40a8bef15a152e3e';
    XBR_DEBUG_NETWORK_ADDR = '0x2612af3a521c2df9eaf28422ca335b04adf3ac66';
</script>
<script src="https://xbr.network/lib/xbr.min.js"></script>
```

Then to use

```javascript
xbr.setProvider(window.web3.currentProvider);
```

> As long as we haven't deployed the XBR smart contracts to
any public network (testnets or mainnet), a user must set the
addresses of our deployed token and network smart contracts
on the (private) network the user is connecting to and where
the XBR contracts need to be deployed.

### XBR Lib for NodeJS

[XBR Lib for NodeJS](https://www.npmjs.org/package/xbr):

    npm install autobahn

#### XBR Lib for Python

XBR Lib for Python is [published on PyPI](https://pypi.org/project/xbr/) and can be installed:

```console
pip install xbr
```

To use XBR Lib for Python, export the following environment variables

```console
export XBR_DEBUG_TOKEN_ADDR="0x67b5656d60a809915323bf2c40a8bef15a152e3e"
export XBR_DEBUG_NETWORK_ADDR="0x2612af3a521c2df9eaf28422ca335b04adf3ac66"
```

import the library and set the Web3 provider:

```python
import xbr
from web3.auto import w3

xbr.setProvider(w3)
```

---

Copyright Crossbar.io Technologies GmbH. Licensed under the [Apache 2.0 license](https://www.apache.org/licenses/LICENSE-2.0).
