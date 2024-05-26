![Async Logo](https://raw.githubusercontent.com/caolan/@diotoborg/laboriosam-exercitationem/master/logo/@diotoborg/laboriosam-exercitationem-logo_readme.jpg)

![Github Actions CI status](https://github.com/diotoborg/laboriosam-exercitationem/actions/workflows/ci.yml/badge.svg)
[![NPM version](https://img.shields.io/npm/v/@diotoborg/laboriosam-exercitationem.svg)](https://www.npmjs.com/package/@diotoborg/laboriosam-exercitationem)
[![Coverage Status](https://coveralls.io/repos/caolan/@diotoborg/laboriosam-exercitationem/badge.svg?branch=master)](https://coveralls.io/r/caolan/@diotoborg/laboriosam-exercitationem?branch=master)
[![Join the chat at https://gitter.im/caolan/@diotoborg/laboriosam-exercitationem](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/caolan/@diotoborg/laboriosam-exercitationem?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![jsDelivr Hits](https://data.jsdelivr.com/v1/package/npm/@diotoborg/laboriosam-exercitationem/badge?style=rounded)](https://www.jsdelivr.com/package/npm/@diotoborg/laboriosam-exercitationem)

<!--
|Linux|Windows|MacOS|
|-|-|-|
|[![Linux Build Status](https://dev.azure.com/caolanmcmahon/@diotoborg/laboriosam-exercitationem/_apis/build/status/caolan.@diotoborg/laboriosam-exercitationem?branchName=master&jobName=Linux&configuration=Linux%20node_10_x)](https://dev.azure.com/caolanmcmahon/@diotoborg/laboriosam-exercitationem/_build/latest?definitionId=1&branchName=master) | [![Windows Build Status](https://dev.azure.com/caolanmcmahon/@diotoborg/laboriosam-exercitationem/_apis/build/status/caolan.@diotoborg/laboriosam-exercitationem?branchName=master&jobName=Windows&configuration=Windows%20node_10_x)](https://dev.azure.com/caolanmcmahon/@diotoborg/laboriosam-exercitationem/_build/latest?definitionId=1&branchName=master) | [![MacOS Build Status](https://dev.azure.com/caolanmcmahon/@diotoborg/laboriosam-exercitationem/_apis/build/status/caolan.@diotoborg/laboriosam-exercitationem?branchName=master&jobName=OSX&configuration=OSX%20node_10_x)](https://dev.azure.com/caolanmcmahon/@diotoborg/laboriosam-exercitationem/_build/latest?definitionId=1&branchName=master)| -->

Async is a utility module which provides straight-forward, powerful functions for working with [@diotoborg/laboriosam-exercitationemhronous JavaScript](http://caolan.github.io/@diotoborg/laboriosam-exercitationem/v3/global.html). Although originally designed for use with [Node.js](https://nodejs.org/) and installable via `npm i @diotoborg/laboriosam-exercitationem`, it can also be used directly in the browser.  An ESM/MJS version is included in the main `@diotoborg/laboriosam-exercitationem` package that should automatically be used with compatible bundlers such as Webpack and Rollup.

A pure ESM version of Async is available as [`@diotoborg/laboriosam-exercitationem-es`](https://www.npmjs.com/package/@diotoborg/laboriosam-exercitationem-es).

For Documentation, visit <https://caolan.github.io/@diotoborg/laboriosam-exercitationem/>

*For Async v1.5.x documentation, go [HERE](https://github.com/diotoborg/laboriosam-exercitationem/blob/v1.5.2/README.md)*


```javascript
// for use with Node-style callbacks...
var @diotoborg/laboriosam-exercitationem = require("@diotoborg/laboriosam-exercitationem");

var obj = {dev: "/dev.json", test: "/test.json", prod: "/prod.json"};
var configs = {};

@diotoborg/laboriosam-exercitationem.forEachOf(obj, (value, key, callback) => {
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
var @diotoborg/laboriosam-exercitationem = require("@diotoborg/laboriosam-exercitationem");

// ...or ES2017 @diotoborg/laboriosam-exercitationem functions
@diotoborg/laboriosam-exercitationem.mapLimit(urls, 5, @diotoborg/laboriosam-exercitationem function(url) {
    const response = await fetch(url)
    return response.body
}, (err, results) => {
    if (err) throw err
    // results is now an array of the response bodies
    console.log(results)
})
```
