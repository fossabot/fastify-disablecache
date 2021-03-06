# fastify-disablecache

[![GitHub Release](https://img.shields.io/github/release/Fdawgs/fastify-disablecache.svg)](https://github.com/Fdawgs/fastify-disablecache/releases/latest/) [![npm version](https://img.shields.io/npm/v/fastify-disablecache)](https://www.npmjs.com/package/fastify-disablecache) ![Build Status](https://github.com/Fdawgs/fastify-disablecache/workflows/CI/badge.svg?branch=master) [![Coverage Status](https://coveralls.io/repos/github/Fdawgs/fastify-disablecache/badge.svg?branch=master)](https://coveralls.io/github/Fdawgs/fastify-disablecache?branch=master) [![Known Vulnerabilities](https://snyk.io/test/github/Fdawgs/fastify-disablecache/badge.svg)](https://snyk.io/test/github/Fdawgs/fastify-disablecache) [![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat)](https://github.com/prettier/prettier)
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FFdawgs%2Ffastify-disablecache.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2FFdawgs%2Ffastify-disablecache?ref=badge_shield)

> Fastify plugin to disable client-side caching

## Intro

Inspired by [nocache](https://github.com/helmetjs/nocache), the `fastify-disablecache` plugin sets the following response headers and values to disable client-side caching:

```
Surrogate-Control: no-store
Cache-Control: no-store, no-cache, must-revalidate, proxy-revalidate
Pragma: no-cache
Expires: 0
```

You can read more about these response headers on [MDN here](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers#caching).

This plugin was created out of a need for an easy way to disable client-side caching for data recieved from backend APIs at [Yeovil District Hospital NHS Foundation Trust](https://yeovilhospital.co.uk/). This ensures patient data is always current when called by applications.

## Installation

Install using [`npm`](https://www.npmjs.com/package/fastify-disablecache):

```bash
npm install fastify-disablecache
```

Or [`yarn`](https://yarnpkg.com/en/package/fastify-disablecache):

```bash
yarn add fastify-disablecache
```

fastify-disablecache's test scripts use npm commands.

## Example Usage

```js
const Fastify = require("fastify");
const disableCache = require("fastify-disablecache");

const server = Fastify();
server.register(disableCache);

server.get("/", (req, res) => {
	res.send("ok");
});

server.listen(3000);
```

## Contributing

Please see [CONTRIBUTING.md](https://github.com/Fdawgs/fastify-disablecache/blob/master/CONTRIBUTING.md) for more details regarding contributing to this project.

## Acknowledgements

-   [**Evan Hahn**](https://github.com/EvanHahn) - [nocache](https://github.com/helmetjs/helmet) developer
-   [**Matteo Collina**](https://github.com/mcollina) - Optimisation suggestions

## License

`fastify-disablecache` is licensed under the [MIT](https://github.com/Fdawgs/fastify-disablecache/blob/master/LICENSE) license.


[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FFdawgs%2Ffastify-disablecache.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2FFdawgs%2Ffastify-disablecache?ref=badge_large)