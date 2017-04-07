# api documentation for  [gulp-jsbeautifier (v2.1.0)](https://github.com/tarunc/gulp-jsbeautifier)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-jsbeautifier.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-jsbeautifier) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-jsbeautifier.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-jsbeautifier)
#### jsbeautifier.org for Gulp

[![NPM](https://nodei.co/npm/gulp-jsbeautifier.png?downloads=true)](https://www.npmjs.com/package/gulp-jsbeautifier)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-jsbeautifier/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gulp-jsbeautifier_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-jsbeautifier/build/apidoc.html)

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
            "name": "biasso",
            "email": "simone.biassoni@outlook.com"
        },
        {
            "name": "tarunc",
            "email": "tarunc92@gmail.com"
        }
    ],
    "name": "gulp-jsbeautifier",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gulp-jsbeautifier](#apidoc.module.gulp-jsbeautifier)
1.  [function <span class="apidocSignatureSpan">gulp-jsbeautifier.</span>reporter (options)](#apidoc.element.gulp-jsbeautifier.reporter)
1.  [function <span class="apidocSignatureSpan">gulp-jsbeautifier.</span>validate (options)](#apidoc.element.gulp-jsbeautifier.validate)
1.  object <span class="apidocSignatureSpan">gulp-jsbeautifier.</span>report



# <a name="apidoc.module.gulp-jsbeautifier"></a>[module gulp-jsbeautifier](#apidoc.module.gulp-jsbeautifier)

#### <a name="apidoc.element.gulp-jsbeautifier.reporter"></a>[function <span class="apidocSignatureSpan">gulp-jsbeautifier.</span>reporter (options)](#apidoc.element.gulp-jsbeautifier.reporter)
- description and source-code
```javascript
function reporter(options) {
  var verbosity = 0;
  var errorCount = 0;

  if (typeof options === 'object' && Object.prototype.hasOwnProperty.call(options, 'verbosity')) {
    verbosity = options.verbosity;
  }

  return through.obj(function (file, encoding, callback) {
    if (file.jsbeautify) {
      if (verbosity >= 1 && file.jsbeautify.type === null) {
        log('Can not beautify ' + gutil.colors.cyan(file.relative));
      } else if (verbosity >= 0 && file.jsbeautify.beautified) {
        log('Beautified ' + gutil.colors.cyan(file.relative) + ' [' + file.jsbeautify.type + ']');
      } else if (verbosity >= 0 && file.jsbeautify.canBeautify) {
        errorCount += 1;
        log('Can beautify ' + gutil.colors.cyan(file.relative) + ' [' + file.jsbeautify.type + ']');
      } else if (verbosity >= 1) {
        log('Already beautified ' + gutil.colors.cyan(file.relative) + ' [' + file.jsbeautify.type + ']');
      }
    }

    callback(null, file);
  }, function flush(callback) {
    if (errorCount > 0) {
      this.emit('error', new PluginError(PLUGIN_NAME, 'Validation not passed. Please beautify.'));
    }
    callback();
  });
}
```
- example usage
```shell
...
'''javascript
var gulp = require('gulp');
var prettify = require('gulp-jsbeautifier');

gulp.task('validate', function() {
  return gulp.src(['./*.css', './*.html', './*.js'])
    .pipe(prettify.validate())
    .pipe(prettify.reporter())
});
'''

## Reporter
Lists files that have been beautified, those already beautified, and those that can not be beautified.
If the [validate](#validate) feature is used, the reporter lists files that can be beautified and emits an error before the stream
 ends if such a file was detected.
...
```

#### <a name="apidoc.element.gulp-jsbeautifier.validate"></a>[function <span class="apidocSignatureSpan">gulp-jsbeautifier.</span>validate (options)](#apidoc.element.gulp-jsbeautifier.validate)
- description and source-code
```javascript
function validate(options) {
  return helper(options, true);
}
```
- example usage
```shell
...

'''javascript
var gulp = require('gulp');
var prettify = require('gulp-jsbeautifier');

gulp.task('validate', function() {
  return gulp.src(['./*.css', './*.html', './*.js'])
    .pipe(prettify.validate())
    .pipe(prettify.reporter())
});
'''

## Reporter
Lists files that have been beautified, those already beautified, and those that can not be beautified.
If the [validate](#validate) feature is used, the reporter lists files that can be beautified and emits an error before the stream
 ends if such a file was detected.
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
