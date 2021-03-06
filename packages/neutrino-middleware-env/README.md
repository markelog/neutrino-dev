# Neutrino Environment Middleware
[![NPM version][npm-image]][npm-url] [![NPM downloads][npm-downloads]][npm-url] [![Join Slack][slack-image]][slack-url]

`neutrino-middleware-env` is Neutrino middleware for injecting environment variable definitions into
source code at `process.env`. Always injects `process.env.NODE_ENV`, unless overridden.

## Requirements

- Node.js v6.10+
- Yarn or npm client
- Neutrino v6

## Installation

`neutrino-middleware-env` can be installed via the Yarn or npm clients.

#### Yarn

```bash
❯ yarn add neutrino-middleware-env
```

#### npm

```bash
❯ npm install --save neutrino-middleware-env
```

## Usage

`neutrino-middleware-env` can be consumed from the Neutrino API, middleware, or presets. Require this package
and plug it into Neutrino:

```js
// Using function middleware format
const env = require('neutrino-middleware-env');

// Use with default options
neutrino.use(env);

// Usage with additional environment variables
neutrino.use(env, ['SECRET_KEY']);
```

```js
// Using object or array middleware format

// Use with default options
module.exports = {
  use: ['neutrino-middleware-env']
};

// Usage with additional environment variables
module.exports = {
  use: [
    ['neutrino-middleware-env', ['SECRET_KEY']]
  ]
};
```

This middleware optionally accepts an array of environment variables to additionally inject into source code.

## Customization

`neutrino-middleware-env` creates some conventions to make overriding the configuration easier once you are ready to
make changes.

### Plugins

The following is a list of plugins and their identifiers which can be overridden:

| Name | Description | Environments |
| ---- | ----------- | ------------ |
| `env` | Inject environment variables into source code at `process.env`. | all |

## Contributing

This middleware is part of the [neutrino-dev](https://github.com/mozilla-neutrino/neutrino-dev) repository, a monorepo
containing all resources for developing Neutrino and its core presets and middleware. Follow the
[contributing guide](https://neutrino.js.org/contributing) for details.

[npm-image]: https://img.shields.io/npm/v/neutrino-middleware-env.svg
[npm-downloads]: https://img.shields.io/npm/dt/neutrino-middleware-env.svg
[npm-url]: https://npmjs.org/package/neutrino-middleware-env
[slack-image]: https://neutrino-slack.herokuapp.com/badge.svg
[slack-url]: https://neutrino-slack.herokuapp.com/
