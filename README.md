# npmdoc-gulp-jsbeautifier

#### api documentation for  [gulp-jsbeautifier (v2.1.0)](https://github.com/tarunc/gulp-jsbeautifier)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-jsbeautifier.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-jsbeautifier) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-jsbeautifier.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-jsbeautifier)

#### jsbeautifier.org for Gulp

[![NPM](https://nodei.co/npm/gulp-jsbeautifier.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/gulp-jsbeautifier)

- [https://npmdoc.github.io/node-npmdoc-gulp-jsbeautifier/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-gulp-jsbeautifier/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-jsbeautifier/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-jsbeautifier/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-jsbeautifier/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-jsbeautifier/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Tarun Chaudhry",
        "url": "https://github.com/tarunc"
    },
    "bugs": {
        "url": "https://github.com/tarunc/gulp-jsbeautifier/issues"
    },
    "contributors": [
        {
            "name": "Simone Biassoni",
            "url": "https://github.com/biasso"
        },
        {
            "name": "Denny Ayard",
            "url": "https://github.com/djayard"
        }
    ],
    "dependencies": {
        "gulp-util": "^3.0.8",
        "js-beautify": "^1.6.11",
        "lodash": "^4.17.4",
        "rc": "^1.1.7",
        "through2": "^2.0.3"
    },
    "description": "jsbeautifier.org for Gulp",
    "devDependencies": {
        "chai": "^3.5.0",
        "coveralls": "^2.12.0",
        "del": "^2.2.2",
        "eslint": "^3.17.1",
        "eslint-config-airbnb-base": "^11.1.1",
        "eslint-plugin-import": "^2.2.0",
        "istanbul": "^0.4.5",
        "mocha": "^3.2.0",
        "sinon": "^1.17.7"
    },
    "directories": {},
    "dist": {
        "shasum": "fc5596e59113c5a71f17a66727f3914df2e59054",
        "tarball": "https://registry.npmjs.org/gulp-jsbeautifier/-/gulp-jsbeautifier-2.1.0.tgz"
    },
    "engines": {
        "node": ">=0.10.0"
    },
    "files": [
        "CHANGELOG.md",
        "LICENSE.md",
        "README.md",
        "index.js"
    ],
    "gitHead": "1510a552d17eaf7481cd67a8ba47180dce96f5aa",
    "homepage": "https://github.com/tarunc/gulp-jsbeautifier",
    "keywords": [
        "beautify",
        "format",
        "gulp",
        "js-beautify",
        "gulpplugin",
        "html beautify",
        "html format",
        "html indent",
        "html prettify",
        "prettify",
        "beautifier",
        "jsbeautifier",
        "code-quality",
        "javascript beautify",
        "css beautify",
        "json beautify"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "biasso"
        },
        {
            "name": "tarunc"
        }
    ],
    "name": "gulp-jsbeautifier",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/tarunc/gulp-jsbeautifier.git"
    },
    "scripts": {
        "cover": "istanbul cover _mocha",
        "coveralls": "istanbul cover _mocha --report lcovonly -- -R spec && cat ./coverage/lcov.info | coveralls && rm -rf ./coverage",
        "lint": "eslint . --ignore-path .gitignore",
        "test": "mocha"
    },
    "version": "2.1.0"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
