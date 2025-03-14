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

Auto-commit on 2025-02-20 15:26:19 | rand=77075

Auto-commit on 2025-02-20 15:38:26 | rand=55780

Auto-commit on 2025-02-20 15:50:33 | rand=8354

Auto-commit on 2025-02-20 16:02:41 | rand=30793

Auto-commit on 2025-02-20 16:14:44 | rand=99633

Auto-commit on 2025-02-20 16:26:50 | rand=86298

Auto-commit on 2025-02-20 16:38:58 | rand=57621

Auto-commit on 2025-02-20 16:51:02 | rand=87710

Auto-commit on 2025-02-20 17:03:13 | rand=63152

Auto-commit on 2025-02-21 15:16:51 | rand=24444

Auto-commit on 2025-02-21 15:28:56 | rand=98259

Auto-commit on 2025-02-21 15:40:54 | rand=88402

Auto-commit on 2025-02-21 15:52:53 | rand=43565

Auto-commit on 2025-02-21 16:04:48 | rand=24152

Auto-commit on 2025-02-21 16:16:45 | rand=31792

Auto-commit on 2025-02-21 16:28:45 | rand=8095

Auto-commit on 2025-02-21 16:40:50 | rand=64029

Auto-commit on 2025-02-21 16:52:53 | rand=2335

Auto-commit on 2025-02-21 17:04:49 | rand=35263

Auto-commit on 2025-02-21 17:16:50 | rand=34291

Auto-commit on 2025-02-21 17:28:51 | rand=72791

Auto-commit on 2025-02-21 17:40:48 | rand=61858

Auto-commit on 2025-02-21 17:52:46 | rand=74527

Auto-commit on 2025-02-21 18:04:47 | rand=40830

Auto-commit on 2025-02-22 00:23:02 | rand=64236

Auto-commit on 2025-02-22 00:35:12 | rand=31740

Auto-commit on 2025-02-22 00:47:14 | rand=42046

Auto-commit on 2025-02-22 00:59:15 | rand=59555

Auto-commit on 2025-02-22 01:11:18 | rand=12572

Auto-commit on 2025-02-22 01:23:26 | rand=73798

Auto-commit on 2025-02-22 01:35:25 | rand=84397

Auto-commit on 2025-02-22 01:47:30 | rand=72512

Auto-commit on 2025-02-22 01:59:29 | rand=23569

Auto-commit on 2025-02-22 02:11:37 | rand=22723

Auto-commit on 2025-02-22 02:23:44 | rand=89796

Auto-commit on 2025-02-22 02:35:51 | rand=23321

Auto-commit on 2025-02-22 02:47:57 | rand=56809

Auto-commit on 2025-02-22 02:59:56 | rand=6922

Auto-commit on 2025-02-22 03:12:14 | rand=56842

Auto-commit on 2025-02-22 14:52:12 | rand=96363

Auto-commit on 2025-02-22 15:04:18 | rand=66485

Auto-commit on 2025-02-22 15:16:24 | rand=40954

Auto-commit on 2025-02-22 15:28:29 | rand=40244

Auto-commit on 2025-02-22 15:40:29 | rand=11853

Auto-commit on 2025-02-22 15:52:36 | rand=69798

Auto-commit on 2025-02-22 16:04:41 | rand=19363

Auto-commit on 2025-02-22 16:16:40 | rand=78024

Auto-commit on 2025-02-22 16:28:41 | rand=99854

Auto-commit on 2025-02-22 16:40:42 | rand=72084

Auto-commit on 2025-02-22 16:52:46 | rand=3725

Auto-commit on 2025-02-22 17:04:46 | rand=85582

Auto-commit on 2025-02-22 17:16:56 | rand=88740

Auto-commit on 2025-02-22 17:28:57 | rand=52378

Auto-commit on 2025-02-22 17:41:02 | rand=41180

Auto-commit on 2025-02-24 13:55:50 | rand=78434

Auto-commit on 2025-02-24 14:07:52 | rand=11777

Auto-commit on 2025-02-24 14:19:51 | rand=84309

Auto-commit on 2025-02-24 14:31:57 | rand=94576

Auto-commit on 2025-02-24 14:44:04 | rand=63149

Auto-commit on 2025-02-24 14:56:04 | rand=12329

Auto-commit on 2025-02-24 15:08:12 | rand=81668

Auto-commit on 2025-02-24 15:20:15 | rand=39068

Auto-commit on 2025-02-24 15:32:25 | rand=2852

Auto-commit on 2025-02-24 15:44:35 | rand=69147

Auto-commit on 2025-02-24 15:56:44 | rand=98866

Auto-commit on 2025-02-24 16:08:45 | rand=80396

Auto-commit on 2025-02-24 16:20:41 | rand=37170

Auto-commit on 2025-02-24 16:32:48 | rand=12381

Auto-commit on 2025-02-24 16:44:53 | rand=13481

Auto-commit on 2025-02-24 17:57:04 | rand=65270

Auto-commit on 2025-02-24 18:09:03 | rand=46372

Auto-commit on 2025-02-24 18:21:09 | rand=25507

Auto-commit on 2025-02-24 18:33:15 | rand=87389

Auto-commit on 2025-02-24 18:45:24 | rand=33515

Auto-commit on 2025-02-24 18:57:28 | rand=84595

Auto-commit on 2025-02-24 19:09:39 | rand=37404

Auto-commit on 2025-02-24 19:21:43 | rand=38093

Auto-commit on 2025-02-24 19:33:42 | rand=45675

Auto-commit on 2025-02-24 19:45:43 | rand=29548

Auto-commit on 2025-02-24 19:57:48 | rand=69043

Auto-commit on 2025-02-24 20:09:53 | rand=93241

Auto-commit on 2025-02-24 20:21:56 | rand=12271

Auto-commit on 2025-02-24 20:33:56 | rand=63018

Auto-commit on 2025-02-24 20:46:00 | rand=10422

Auto-commit on 2025-02-25 12:19:44 | rand=92954

Auto-commit on 2025-02-25 12:31:44 | rand=90168

Auto-commit on 2025-02-25 12:43:52 | rand=73564

Auto-commit on 2025-02-25 12:55:53 | rand=42107

Auto-commit on 2025-02-25 13:07:55 | rand=86011

Auto-commit on 2025-02-25 13:20:03 | rand=25914

Auto-commit on 2025-02-25 13:32:10 | rand=34405

Auto-commit on 2025-02-25 13:44:08 | rand=80188

Auto-commit on 2025-02-25 13:56:12 | rand=80423

Auto-commit on 2025-02-25 14:08:13 | rand=7990

Auto-commit on 2025-02-25 14:20:19 | rand=3883

Auto-commit on 2025-02-25 14:32:23 | rand=56237

Auto-commit on 2025-02-25 14:44:30 | rand=45054

Auto-commit on 2025-02-25 14:56:33 | rand=98969

Auto-commit on 2025-02-25 15:08:41 | rand=88423

Auto-commit on 2025-03-06 14:49:40 | rand=16785

Auto-commit on 2025-03-06 15:01:04 | rand=95832

Auto-commit on 2025-03-06 15:12:22 | rand=8989

Auto-commit on 2025-03-06 15:48:46 | rand=30065

Auto-commit on 2025-03-06 16:00:01 | rand=36746

Auto-commit on 2025-03-06 16:11:21 | rand=20588

Auto-commit on 2025-03-06 16:22:37 | rand=739

Auto-commit on 2025-03-06 16:33:55 | rand=83249

Auto-commit on 2025-03-06 16:45:12 | rand=96127

Auto-commit on 2025-03-06 16:56:30 | rand=97575

Auto-commit on 2025-03-06 19:56:42 | rand=67512

Auto-commit on 2025-03-06 20:36:47 | rand=83852

Auto-commit on 2025-03-06 20:48:31 | rand=3253

Auto-commit on 2025-03-06 20:59:56 | rand=81911
