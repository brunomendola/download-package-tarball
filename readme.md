# download-package-tarball 

Download a node package as a tarball, for example from github or npm

## Installation

Download node at [nodejs.org](http://nodejs.org) and install it, if you haven't already.

```sh
npm install download-package-tarball --save
```

## Usage

```js
/* eslint-disable import/no-extraneous-dependencies */

import download from 'download-package-tarball';

download({
  // a npm tarball url will work
  url: 'https://registry.npmjs.org/snappy/-/snappy-5.0.5.tgz',
  dir: '/dir/where/file/will/be/downloaded'
}).then(() => {
  console.log('file is now downloaded!');
}).catch(err => {
  console.log('oh crap the file could not be downloaded properly');
  console.log(err);
});

download({
  // ... but also a github tarball url
  url: 'https://api.github.com/repos/kesla/node-snappy/tarball/master',
  dir: '/dir/where/file/will/be/downloaded',
  // custom options that will be forwarded to got.stream(..., opts) can also be set
  gotOpts: {
    headers: {
      beep: 'boop'
    }
  }
}).then(() => {
  console.log('file is now downloaded!');
}).catch(err => {
  console.log('oh crap the file could not be downloaded properly');
  console.log(err);
});

download({
  // or a tar file somewhere
  url: 'http://link-to-tarball/file.tar',
  dir: '/dir/where/file/will/be/downloaded'
}).then(() => {
  console.log('file is now downloaded!');
}).catch(err => {
  console.log('oh crap the file could not be downloaded properly');
  console.log(err);
});

```

## Tests

```sh
npm install
npm test
```

## Dependencies

- [download-tarball](https://github.com/kesla/download-tarball): Download a tarball (optionally gzipped) to a folder &amp; extract it in the process. Uses the wonderful &amp; super quick tar-fs &amp; gunzip-maybe libraries.
- [mkdirp-then](https://github.com/fs-utils/mkdirp-then): mkdirp as promised
- [mz](https://github.com/normalize/mz): modernize node.js to current ECMAScript standards
- [npm-package-arg](https://github.com/npm/npm-package-arg): Parse the things that can be arguments to `npm install`
- [rimraf-then](https://github.com/fs-utils/rimraf-then): rimraf as promised
- [then-read-json](https://github.com/tunnckocore/then-read-json): Read JSON file using promises
- [then-tmp](https://github.com/kesla/then-tmp): Promised version of the node.js [tmp](https://www.npmjs.com/package/tmp) module.

## Dev Dependencies

- [babel-cli](https://github.com/babel/babel/tree/master/packages): Babel command line.
- [babel-core](https://github.com/babel/babel/tree/master/packages): Babel compiler core.
- [babel-plugin-syntax-async-functions](https://github.com/babel/babel/tree/master/packages): Allow parsing of async functions
- [babel-plugin-transform-async-to-generator](https://github.com/babel/babel/tree/master/packages): Turn async functions into ES2015 generators
- [babel-preset-es2015-node4](https://github.com/jbach/babel-preset-es2015-node4): Babel preset to make node@4 ES2015 compatible.
- [babel-tape-runner](https://github.com/wavded/babel-tape-runner): Babel + Tape for running your ES Next tests
- [http-test-server](https://github.com/kesla/test-http-server): Create a simple http server for tests
- [package-json-to-readme](https://github.com/zeke/package-json-to-readme): Generate a README.md from package.json contents
- [tapava](https://github.com/kesla/tapava): the syntax of ava, run through tape
- [tar-stream](https://github.com/mafintosh/tar-stream): tar-stream is a streaming tar parser and generator and nothing else. It is streams2 and operates purely using streams which means you can easily extract/parse tarballs without ever hitting the file system.
- [xo](https://github.com/sindresorhus/xo): JavaScript happiness style linter ❤️


## License

MIT

_Generated by [package-json-to-readme](https://github.com/zeke/package-json-to-readme)_
