# bch-js

[![Build Status](https://travis-ci.org/christroutner/bch-js.svg?branch=master)](https://travis-ci.org/christroutner/bch-js)
[![Version](https://img.shields.io/npm/v/@chris.troutner/bch-js)](https://www.npmjs.com/package/@chris.troutner/bch-js)
[![Downloads/week](https://img.shields.io/npm/dw/@chris.troutner/bch-js)](https://npmjs.org/package/@chris.troutner/bch-js)
[![License](https://img.shields.io/npm/l/@chris.troutner/bch-js)](https://github.com/christroutner/bch-js/blob/master/LICENSE.md)

[bch-js](https://www.npmjs.com/package/@chris.troutner/bch-js) is a JavaScript npm library for creating web and mobile apps for interacting with the Bitcoin Cash (BCH) blockchain. It can be used for free, but requires an account on [FullStack.cash](https://fullstack.cash) for increased rate limits. Find out more from [this article](https://troutsblog.com/research/bitcoin-cash/how-to-bch-full-stack-developer)

### Quick Links
- [Documentation](https://bchjs.cash/bch-js/index.html)
- [Examples](https://github.com/Permissionless-Software-Foundation/bch-js-examples)
- [api.fullstack.cash](https://api.fullstack.cash) - REST API this library talks to by default.
- [FullStack.cash Account](https://fullstack.cash/login) - Get your API key to unlock increased rate limits.
- [FullStack.cash](https://fullstack.cash) - a turn-key full-stack solution for application
developers.
- [Permissionless Software Foundation](https://psfoundation.cash) - The organization that maintains this library.


### Quick Notes
- [npm library](https://www.npmjs.com/package/@chris.troutner/bch-js)
  - v2.x.x: JWT token access implemented for [api.bchjs.cash](https://api.bchjs.cash) with paid access at [account.bchjs.cash](https://account.bchjs.cash) to increase rate limits.

- Install library: `npm install @chris.troutner/bch-js`

- Instantiate the library in your code:
```
const BCHJS = require("@chris.troutner/bch-js")
let bchjs = new BCHJS({ restURL: 'https://api.fullstack.cash/v3/' })

// testnet
bchjs = new BCHJS({ restURL: 'https://tapi.fullstack.cash/v3/' })
```

This is a fork of the [BITBOX SDK](https://github.com/Bitcoin-com/bitbox-sdk) (which is maintained by Bitcoin.com). This library is intended to be paired with
the [bch-api](https://github.com/christroutner/bch-api) REST API.

If you need a backward-compatible instance of this library, you can use a
'shim'. Do it like this:
```
const BCHJS = require("@chris.troutner/bch-js")
const bitbox = BCHJS.BitboxShim({ restURL: 'https://api.fullstack.cash/v3/' })
```

### API Key
The [bch-api](https://github.com/christroutner/bch-api) REST API hosted by [FullStack.cash](https://fullstack.cash) uses JWT tokens to pay for increased
rate limits when interacting with a REST API. See [this article](https://troutsblog.com/research/bitcoin-cash/how-to-bch-full-stack-developer) for more information. The JWT token can be fed to bch-js *implicitly* or *explicitly*.

- Implicitly: bch-js will detect your JWT token by setting the `BCHJSTOKEN` environment variable.
- Explicitly: You can directly feed in the JWT token with the `apiToken` property when instantiating the library. Here is an example:

```
const BCHJS = require("@chris.troutner/bch-js")
let bchjs = new BCHJS({
  restURL: 'https://api.fullstack.cash/v3/',
  apiToken: 'eyJhbGciO...'
})
```

## Features
This library sets itself apart from BITBOX with the following features:

- [ECMAScript 2017 standard JavaScript](https://en.wikipedia.org/wiki/ECMAScript#8th_Edition_-_ECMAScript_2017) used instead of TypeScript. Works
natively with node.js v10 or higher.

- [slp-sdk](https://github.com/Bitcoin-com/slp-sdk) features are integrated
into this library too, though not fully working. If you need SLP token functionality,
you should use slp-sdk or [slp-cli-wallet](https://www.npmjs.com/package/slp-cli-wallet).

- [Semantic Release](https://github.com/semantic-release/semantic-release) for
continuous delivery using semantic versioning.

- [Greenkeeper](https://greenkeeper.io/) automatic dependency management for
automatically maintaining the latest, most secure dependencies.

- [IPFS uploads](https://ipfs.io) of all files and dependencies, to backup
dependencies in case they are ever inaccessible from GitHub or npm.



## Documentation:

Full documentation for this library can be found here:
- [Documentation](https://bchjs.cash/bch-js/index.html)

Original documentation on BITBOX is available at:

- [General docs](https://developer.bitcoin.com)
- [BITBOX Introduction](https://developer.bitcoin.com/bitbox)
- [BITBOX API Reference](https://developer.bitcoin.com/bitbox/docs/getting-started)


bch-js uses [APIDOC](http://apidocjs.com/) so that documentation and working code
live in the same repository. To generate the documentation:
- `npm run docs`
- Open the generated `docs/index.html` file in a web browser.

## Support
Have questions? Need help? Join our community support
[Telegram channel](https://t.me/bch_js_toolkit)

## IPFS Releases

I will periodically publish IPFS releases of this repository, including all
dependencies in the `node_modules` folder. This ensures working copies of this
repository can be retrieved in case there is any drift in dependency files, or
if dependencies are pulled from npm or GitHub.

- Initial fork on 5/9/2019:
  - without node_modules folder: QmQFHfbBQdEHfhtiRLbXtX1NcgnfL45hZb7TbQimTXAuzG (4 MB)
  - with node_modules folder: QmXq9Ds6Qdkg9xbRhcF8pay9KabA6QN2y7bx3wvSqiXifk (107 MB)

- v1.0.0 - refactored to pure JavaScript:
  - without node_modules folder: QmNjFsiTZRMAUa9rZpXqZqivv9JLaNicwLSPHjyLB7PVDk (1 MB)
  - with node_modules folder: Qma9ScApwBtuL7dpdSk7jpBFTxbqRdiR921WjyP75SU7bT (100 MB)

## License
[MIT](LICENSE.md)

a minor change
