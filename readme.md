# parse-otp-message

> Parses OTP messages for a verification code and service provider.

[![NPM](https://img.shields.io/npm/v/parse-otp-message.svg)](https://www.npmjs.com/package/parse-otp-message) [![Build Status](https://travis-ci.org/transitive-bullshit/parse-otp-message.svg?branch=master)](https://travis-ci.org/transitive-bullshit/parse-otp-message) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

- handles hundreds of known services (wechat, google, facebook, whatsapp, uber, grubhub, etc...)
- thorough test suite
- meant for parsing automated sms messages


## Install

```bash
npm install --save parse-otp-message
```


## Usage

```js
const parse = require('parse-otp-message')

const { code, service } = parse('Use 5677 as Microsoft account security code')

// code = '5677
// service = 'microsoft'
```

See the [test suite](https://github.com/transitive-bullshit/parse-otp-message/tree/master/index.test.js) for more examples of the types of messages this module can parse.


## API

### parse(message)

Returns: `Object`

Parses the given message and returns an object containing two fields, `code` and `service`. The auth `code` will be all digits except in some special cases, and the returned `service` will always be lowercase.

If no code or service is found, `undefined` is returned.

#### message

Type: `String`
**Required**

SMS or email message possibly containing an auth code and/or service provider details.


## License

MIT © [Travis Fischer](https://github.com/transitive-bullshit)
