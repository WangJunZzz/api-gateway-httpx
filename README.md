api-gateway-httpx
===========

##  声明
为了适用Vue项目基于httpx做了一点修改。使用方式和httpx一致。
[Httpx](https://github.com/JacksonTian/httpx)
## Installation

```bash
$ npm install api-gateway-httpx --save
```

## Usage

```js
'use strict';

const httpx = require('api-gateway-httpx');

httpx.request('http://www.baidu.com/').then((response) => {
  response.pipe(process.stdout);

  response.on('end', () => {
    process.stdout.write('\n');
  });
}, (err) => {
  // on error
});
```

Or with `co`.

```js
co(function* () {
  var response = yield httpx.request('http://www.baidu.com/');

  response.pipe(process.stdout);

  response.on('end', () => {
    process.stdout.write('\n');
  });
});
```

Or with `async/await`.

```js
(async function () {
  var response = await httpx.request('http://www.baidu.com/');

  response.pipe(process.stdout);

  response.on('end', () => {
    process.stdout.write('\n');
  });
})();
```
