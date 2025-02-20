![Async Logo](https://raw.githubusercontent.com/caolan/async/master/logo/async-logo_readme.jpg)

[![Build Status via Travis CI](https://travis-ci.org/caolan/async.svg?branch=master)](https://travis-ci.org/caolan/async)
[![Build Status via Azure Pipelines](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)
[![NPM version](https://img.shields.io/npm/v/async.svg)](https://www.npmjs.com/package/async)
[![Coverage Status](https://coveralls.io/repos/caolan/async/badge.svg?branch=master)](https://coveralls.io/r/caolan/async?branch=master)
[![Join the chat at https://gitter.im/caolan/async](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/caolan/async?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![jsDelivr Hits](https://data.jsdelivr.com/v1/package/npm/async/badge?style=rounded)](https://www.jsdelivr.com/package/npm/async)

<!--
|Linux|Windows|MacOS|
|-|-|-|
|[![Linux Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Linux&configuration=Linux%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![Windows Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Windows&configuration=Windows%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![MacOS Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=OSX&configuration=OSX%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)| -->

Async is a utility module which provides straight-forward, powerful functions for working with [asynchronous JavaScript](http://caolan.github.io/async/v3/global.html). Although originally designed for use with [Node.js](https://nodejs.org/) and installable via `npm i async`, it can also be used directly in the browser.  A ESM/MJS version is included in the main `async` package that should automatically be used with compatible bundlers such as Webpack and Rollup.

A pure ESM version of Async is available as [`async-es`](https://www.npmjs.com/package/async-es).

For Documentation, visit <https://caolan.github.io/async/>

*For Async v1.5.x documentation, go [HERE](https://github.com/caolan/async/blob/v1.5.2/README.md)*


```javascript
// for use with Node-style callbacks...
var async = require("async");

var obj = {dev: "/dev.json", test: "/test.json", prod: "/prod.json"};
var configs = {};

async.forEachOf(obj, (value, key, callback) => {
    fs.readFile(__dirname + value, "utf8", (err, data) => {
        if (err) return callback(err);
        try {
            configs[key] = JSON.parse(data);
        } catch (e) {
            return callback(e);
        }
        callback();
    });
}, err => {
    if (err) console.error(err.message);
    // configs is now a map of JSON data
    doSomethingWith(configs);
});
```

```javascript
var async = require("async");

// ...or ES2017 async functions
async.mapLimit(urls, 5, async function(url) {
    const response = await fetch(url)
    return response.body
}, (err, results) => {
    if (err) throw err
    // results is now an array of the response bodies
    console.log(results)
})
```

Auto-commit on 2025-02-18 21:04:06 | rand=47087

Auto-commit on 2025-02-18 21:16:59 | rand=79835

Auto-commit on 2025-02-18 21:29:51 | rand=11749

Auto-commit on 2025-02-19 08:19:37 | rand=38316

Auto-commit on 2025-02-19 08:32:33 | rand=13413

Auto-commit on 2025-02-19 08:45:33 | rand=81233

Auto-commit on 2025-02-19 08:58:29 | rand=53047

Auto-commit on 2025-02-19 09:11:19 | rand=58347

Auto-commit on 2025-02-19 09:24:17 | rand=38356

Auto-commit on 2025-02-19 09:37:15 | rand=56644

Auto-commit on 2025-02-19 09:50:13 | rand=16136

Auto-commit on 2025-02-19 10:03:05 | rand=4470

Auto-commit on 2025-02-19 10:16:05 | rand=44288

Auto-commit on 2025-02-19 10:28:54 | rand=43064

Auto-commit on 2025-02-19 10:41:46 | rand=18014

Auto-commit on 2025-02-19 10:54:43 | rand=52730

Auto-commit on 2025-02-19 11:07:36 | rand=7519

Auto-commit on 2025-02-19 11:20:32 | rand=40174

Auto-commit on 2025-02-19 18:31:55 | rand=26805

Auto-commit on 2025-02-19 18:44:54 | rand=69607

Auto-commit on 2025-02-19 18:57:52 | rand=61414

Auto-commit on 2025-02-19 19:10:39 | rand=10930

Auto-commit on 2025-02-19 19:23:39 | rand=4450

Auto-commit on 2025-02-19 19:36:31 | rand=8517

Auto-commit on 2025-02-19 19:49:24 | rand=14311

Auto-commit on 2025-02-19 20:02:22 | rand=86142

Auto-commit on 2025-02-19 20:15:16 | rand=92829

Auto-commit on 2025-02-19 20:28:16 | rand=28617

Auto-commit on 2025-02-19 20:41:08 | rand=15070

Auto-commit on 2025-02-19 20:54:03 | rand=84486

Auto-commit on 2025-02-19 21:07:03 | rand=49179

Auto-commit on 2025-02-19 21:19:57 | rand=99451

Auto-commit on 2025-02-19 21:32:56 | rand=25807

Auto-commit on 2025-02-20 09:38:11 | rand=34977

Auto-commit on 2025-02-20 14:13:59 | rand=85558

Auto-commit on 2025-02-20 14:26:05 | rand=24692

Auto-commit on 2025-02-20 14:38:14 | rand=20059

Auto-commit on 2025-02-20 14:50:15 | rand=665

Auto-commit on 2025-02-20 15:02:12 | rand=99136

Auto-commit on 2025-02-20 15:14:19 | rand=49499
