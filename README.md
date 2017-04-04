# api documentation for  [david (v11.0.0)](https://github.com/alanshaw/david#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-david.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-david) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-david.svg)](https://travis-ci.org/npmdoc/node-npmdoc-david)
#### Node.js module that tells you when your project npm dependencies are out of date.

[![NPM](https://nodei.co/npm/david.png?downloads=true)](https://www.npmjs.com/package/david)

[![apidoc](https://npmdoc.github.io/node-npmdoc-david/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-david_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-david/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-david/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-david/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Alan Shaw"
    },
    "bin": {
        "david": "bin/david.js"
    },
    "bugs": {
        "url": "https://github.com/alanshaw/david/issues"
    },
    "dependencies": {
        "async": "^2.0.1",
        "cli-color-tty": "^2.0.0",
        "cli-table": "^0.3.1",
        "exit": "^0.1.2",
        "minimist": "^1.1.0",
        "npm": "^4.0.3",
        "semver": "^5.3.0",
        "xtend": "^4.0.0"
    },
    "description": "Node.js module that tells you when your project npm dependencies are out of date.",
    "devDependencies": {
        "coveralls": "^2.11.12",
        "istanbul": "^0.4.0",
        "jshint": "^2.5.1",
        "rewire": "^2.1.0",
        "rimraf": "^2.5.4",
        "standard": "^9.0.0",
        "tape": "^4.0.0"
    },
    "directories": {},
    "dist": {
        "shasum": "039da9427072fb7767f4daa56a54eca24dcc2bc3",
        "tarball": "https://registry.npmjs.org/david/-/david-11.0.0.tgz"
    },
    "engines": {
        "node": ">=0.10.1"
    },
    "files": [
        "bin",
        "lib",
        "LICENCE"
    ],
    "gitHead": "90c8beee96cb2cb927e28f18796e2d58c1dd6760",
    "homepage": "https://github.com/alanshaw/david#readme",
    "license": "MIT",
    "main": "lib/david.js",
    "maintainers": [
        {
            "name": "alanshaw",
            "email": "alan138@gmail.com"
        }
    ],
    "name": "david",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/alanshaw/david.git"
    },
    "scripts": {
        "coveralls": "cat ./coverage/lcov.info | coveralls",
        "test": "standard && istanbul cover node_modules/tape/bin/tape test/*.js"
    },
    "version": "11.0.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module david](#apidoc.module.david)
1.  [function <span class="apidocSignatureSpan">david.</span>batch ()](#apidoc.element.david.batch)
1.  [function <span class="apidocSignatureSpan">david.</span>getDependencies (manifest, opts, cb)](#apidoc.element.david.getDependencies)
1.  [function <span class="apidocSignatureSpan">david.</span>getUpdatedDependencies (manifest, opts, cb)](#apidoc.element.david.getUpdatedDependencies)
1.  [function <span class="apidocSignatureSpan">david.</span>isUpdated (dep, opts)](#apidoc.element.david.isUpdated)
1.  object <span class="apidocSignatureSpan">david.</span>batch.prototype
1.  object <span class="apidocSignatureSpan">david.</span>npm
1.  object <span class="apidocSignatureSpan">david.</span>version

#### [module david.batch](#apidoc.module.david.batch)
1.  [function <span class="apidocSignatureSpan">david.</span>batch ()](#apidoc.element.david.batch.batch)

#### [module david.batch.prototype](#apidoc.module.david.batch.prototype)
1.  [function <span class="apidocSignatureSpan">david.batch.prototype.</span>call (key, cb)](#apidoc.element.david.batch.prototype.call)
1.  [function <span class="apidocSignatureSpan">david.batch.prototype.</span>exists (key)](#apidoc.element.david.batch.prototype.exists)
1.  [function <span class="apidocSignatureSpan">david.batch.prototype.</span>push (key, cb)](#apidoc.element.david.batch.prototype.push)

#### [module david.npm](#apidoc.module.david.npm)
1.  [function <span class="apidocSignatureSpan">david.npm.</span>getVersionsInfo (name, opts, cb)](#apidoc.element.david.npm.getVersionsInfo)

#### [module david.version](#apidoc.module.david.version)
1.  [function <span class="apidocSignatureSpan">david.version.</span>getLatest (current, versions, opts)](#apidoc.element.david.version.getLatest)
1.  [function <span class="apidocSignatureSpan">david.version.</span>getLatestStable (versions)](#apidoc.element.david.version.getLatestStable)
1.  [function <span class="apidocSignatureSpan">david.version.</span>getVersionsInRange (range, versions, loose)](#apidoc.element.david.version.getVersionsInRange)
1.  [function <span class="apidocSignatureSpan">david.version.</span>isScm (version)](#apidoc.element.david.version.isScm)
1.  [function <span class="apidocSignatureSpan">david.version.</span>isStable (version)](#apidoc.element.david.version.isStable)



# <a name="apidoc.module.david"></a>[module david](#apidoc.module.david)

#### <a name="apidoc.element.david.batch"></a>[function <span class="apidocSignatureSpan">david.</span>batch ()](#apidoc.element.david.batch)
- description and source-code
```javascript
function Batch() {
  if (!(this instanceof Batch)) return new Batch()
  this._batch = {}
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.david.getDependencies"></a>[function <span class="apidocSignatureSpan">david.</span>getDependencies (manifest, opts, cb)](#apidoc.element.david.getDependencies)
- description and source-code
```javascript
function getDependencies(manifest, opts, cb) {
  manifest = manifest || {}

  // Allow callback to be passed as second parameter
  if (!cb) {
    cb = opts
    opts = {}
  } else {
    opts = opts || {}
  }

  opts.error = opts.error || {}
  opts.ignore = opts.ignore || []

  if (manifest.david && manifest.david.ignore) {
    opts.ignore = opts.ignore.concat(manifest.david.ignore)
  }

  var pkgs = {}
  var deps = normaliseDeps(manifest[depType(opts)] || {})
  var depNames = Object.keys(deps)
  var error // Return any error that occurred but don't stop processing

  if (!depNames.length) {
    return setImmediate(function () { cb(null, pkgs) })
  }

  var tasks = depNames.map(function (depName) {
    return function (cb) {
      if (opts.ignore.indexOf(depName) > -1) {
        return cb()
      }

      var err

      if (Object.prototype.toString.call(deps[depName]) !== '[object String]') {
        err = new Error('Non-string dependency: ' + deps[depName])
        err.code = 'EDEPTYPE'

        if (!opts.error.EDEPTYPE) {
          pkgs[depName] = {required: deps[depName], warn: err}
        } else {
          error = err
        }

        return cb()
      }

      if (Version.isScm(deps[depName])) {
        err = new Error('SCM dependency: ' + deps[depName])
        err.code = 'ESCM'

        if (!opts.error.ESCM) {
          pkgs[depName] = {required: deps[depName], warn: err}
        } else {
          error = err
        }
        return cb()
      }

      Npm.getVersionsInfo(depName, opts, function (err, versionsInfo) {
        if (err) {
          if (!opts.error.E404 && err.code === 'E404') {
            if (err === '404 Not Found') {
              err = new Error('404 Not Found: ' + depName)
              err.pkgid = depName
              err.statusCode = 404
              err.code = 'E404'
            }

            pkgs[depName] = {required: deps[depName], warn: err}
          } else {
            error = err
          }
          return cb()
        }

        try {
          var latestVersionInfo = Version.getLatest(versionsInfo.current, versionsInfo.versions, opts)

          pkgs[depName] = {
            required: deps[depName],
            stable: latestVersionInfo.stable,
            latest: latestVersionInfo.latest
          }

          if (opts.versions) {
            pkgs[depName].versions = versionsInfo.versions
          }

          if (opts.rangeVersions) {
            pkgs[depName].rangeVersions = Version.getVersionsInRange(deps[depName], versionsInfo.versions, opts.loose)
          }
        } catch (err) {
          error = err
        }

        cb()
      })
    }
  })

  parallel(tasks, function () { cb(error, pkgs) })
}
```
- example usage
```shell
...
},
devDependencies: {
  'yyy': '~0.0.0',
  'zzz': '~0.0.0'
}
};

david.getDependencies(manifest, function (er, deps) {
console.log('latest dependencies information for', manifest.name);
listDependencies(deps);
});

david.getDependencies(manifest, { dev: true }, function (er, deps) {
console.log('latest devDependencies information for', manifest.name);
listDependencies(deps);
...
```

#### <a name="apidoc.element.david.getUpdatedDependencies"></a>[function <span class="apidocSignatureSpan">david.</span>getUpdatedDependencies (manifest, opts, cb)](#apidoc.element.david.getUpdatedDependencies)
- description and source-code
```javascript
getUpdatedDependencies = function (manifest, opts, cb) {
  if (!cb) {
    cb = opts
    opts = {}
  } else {
    opts = opts || {}
  }
  opts.error = opts.error || {}

  getDependencies(manifest, opts, function (err, pkgs) {
    if (err) return cb(err)

    // Filter out the non-updated dependencies
    Object.keys(pkgs).forEach(function (depName) {
      if (pkgs[depName].warn) return

      if (!isUpdated(pkgs[depName], opts)) {
        delete pkgs[depName]
      }
    })

    cb(err, pkgs)
  })
}
```
- example usage
```shell
...
});

david.getDependencies(manifest, { dev: true }, function (er, deps) {
console.log('latest devDependencies information for', manifest.name);
listDependencies(deps);
});

david.getUpdatedDependencies(manifest, function (er, deps) {
console.log('dependencies with newer versions for', manifest.name);
listDependencies(deps);
});

david.getUpdatedDependencies(manifest, { dev: true }, function (er, deps) {
console.log('devDependencies with newer versions for', manifest.name);
listDependencies(deps);
...
```

#### <a name="apidoc.element.david.isUpdated"></a>[function <span class="apidocSignatureSpan">david.</span>isUpdated (dep, opts)](#apidoc.element.david.isUpdated)
- description and source-code
```javascript
function isUpdated(dep, opts) {
  opts = opts || {}

  var required = dep.required || '*'

  // TODO: Handle tags correctly
  if (required !== 'latest' && required !== '*') {
    var range = semver.validRange(required, opts.loose) || ''
    var version = opts.stable ? dep.stable : dep.latest

    if (version) {
      if (!range) {
        return true
      } else if (!semver.satisfies(version, range, opts.loose)) {
        if (opts.stable && semver.gtr(version, range, opts.loose)) {
          return true
        } else if (!opts.stable) {
          return true
        }
      }
    }
  }
  return false
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.david.batch"></a>[module david.batch](#apidoc.module.david.batch)

#### <a name="apidoc.element.david.batch.batch"></a>[function <span class="apidocSignatureSpan">david.</span>batch ()](#apidoc.element.david.batch.batch)
- description and source-code
```javascript
function Batch() {
  if (!(this instanceof Batch)) return new Batch()
  this._batch = {}
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.david.batch.prototype"></a>[module david.batch.prototype](#apidoc.module.david.batch.prototype)

#### <a name="apidoc.element.david.batch.prototype.call"></a>[function <span class="apidocSignatureSpan">david.batch.prototype.</span>call (key, cb)](#apidoc.element.david.batch.prototype.call)
- description and source-code
```javascript
call = function (key, cb) {
  var cbs = this._batch[key]
  this._batch[key] = null
  cbs.forEach(cb)
}
```
- example usage
```shell
...
  if (batch.exists(name)) {
    return batch.push(name, cb)
  }

  batch.push(name, cb)

  npm.load(opts.npm || {}, function (err) {
    if (err) return batch.call(name, function (cb) { cb(err) })

    npm.commands.view([name, 'versions', 'time'], true, function (err, data) {
if (err) return batch.call(name, function (cb) { cb(err) })

var currentVersion = Object.keys(data)[0]
var versions = null
...
```

#### <a name="apidoc.element.david.batch.prototype.exists"></a>[function <span class="apidocSignatureSpan">david.batch.prototype.</span>exists (key)](#apidoc.element.david.batch.prototype.exists)
- description and source-code
```javascript
exists = function (key) {
  return this._batch[key] != null
}
```
- example usage
```shell
...
 * get when you 'npm install [package]' and 'versions' is a sorted array of
 * available versions for the dependency.
 * @param {String} name Dependency name
 * @param {Object} opts Options
 * @param {Object} [opts.npm] npm configuration options
 */
function getVersionsInfo (name, opts, cb) {
if (batch.exists(name)) {
  return batch.push(name, cb)
}

batch.push(name, cb)

npm.load(opts.npm || {}, function (err) {
  if (err) return batch.call(name, function (cb) { cb(err) })
...
```

#### <a name="apidoc.element.david.batch.prototype.push"></a>[function <span class="apidocSignatureSpan">david.batch.prototype.</span>push (key, cb)](#apidoc.element.david.batch.prototype.push)
- description and source-code
```javascript
push = function (key, cb) {
  this._batch[key] = this._batch[key] || []
  this._batch[key].push(cb)
}
```
- example usage
```shell
...
/**
* Create or add a callback function to the end of a batch for a given key.
* @param key
* @param cb
*/
Batch.prototype.push = function (key, cb) {
 this._batch[key] = this._batch[key] || []
 this._batch[key].push(cb)
}

/**
* Determine if there is a batch for the given key.
* @param {String} key
* @returns {boolean}
*/
...
```



# <a name="apidoc.module.david.npm"></a>[module david.npm](#apidoc.module.david.npm)

#### <a name="apidoc.element.david.npm.getVersionsInfo"></a>[function <span class="apidocSignatureSpan">david.npm.</span>getVersionsInfo (name, opts, cb)](#apidoc.element.david.npm.getVersionsInfo)
- description and source-code
```javascript
function getVersionsInfo(name, opts, cb) {
  if (batch.exists(name)) {
    return batch.push(name, cb)
  }

  batch.push(name, cb)

  npm.load(opts.npm || {}, function (err) {
    if (err) return batch.call(name, function (cb) { cb(err) })

    npm.commands.view([name, 'versions', 'time'], true, function (err, data) {
      if (err) return batch.call(name, function (cb) { cb(err) })

      var currentVersion = Object.keys(data)[0]
      var versions = null

      // 'npm view 0 versions' returns {}
      if (!currentVersion) {
        return batch.call(name, function (cb) {
          cb(new Error('Failed to get versions for ' + name))
        })
      }

      // Some packages simply don't have a time object
      if (data[currentVersion].time) {
        versions = data[currentVersion].versions.sort(function (a, b) {
          a = data[currentVersion].time[a]
          b = data[currentVersion].time[b]
          return (a < b ? -1 : (a > b ? 1 : 0))
        })
      } else {
        versions = data[currentVersion].versions
      }

      batch.call(name, function (cb) {
        cb(null, { current: currentVersion, versions: versions })
      })
    })
  })
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.david.version"></a>[module david.version](#apidoc.module.david.version)

#### <a name="apidoc.element.david.version.getLatest"></a>[function <span class="apidocSignatureSpan">david.version.</span>getLatest (current, versions, opts)](#apidoc.element.david.version.getLatest)
- description and source-code
```javascript
function getLatest(current, versions, opts) {
  var stable = current
  var latest = versions[versions.length - 1]

  if (!isStable(stable)) {
    stable = getLatestStable(versions)
  }

  // getLatestStable might not have found a stable version
  if (stable) {
    // Latest is the most recent version with higher version than stable
    for (var i = versions.length - 1; i >= 0; i--) {
      // If !opts.loose then this may throw
      if (semver.gt(versions[i], stable, opts.loose)) {
        latest = versions[i]
        break
      }
    }
  }

  return { latest: latest, stable: stable }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.david.version.getLatestStable"></a>[function <span class="apidocSignatureSpan">david.version.</span>getLatestStable (versions)](#apidoc.element.david.version.getLatestStable)
- description and source-code
```javascript
function getLatestStable(versions) {
  versions = versions.slice()
  while (versions.length) {
    var version = versions.pop()
    if (isStable(version)) {
      return version
    }
  }
  return null
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.david.version.getVersionsInRange"></a>[function <span class="apidocSignatureSpan">david.version.</span>getVersionsInRange (range, versions, loose)](#apidoc.element.david.version.getVersionsInRange)
- description and source-code
```javascript
function getVersionsInRange(range, versions, loose) {
  return versions.filter(function (v) {
    return semver.satisfies(v, range, loose)
  })
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.david.version.isScm"></a>[function <span class="apidocSignatureSpan">david.version.</span>isScm (version)](#apidoc.element.david.version.isScm)
- description and source-code
```javascript
function isScm(version) {
  var scmPrefixes = ['git:', 'git+ssh:', 'https:', 'git+https:']
  var blacklisted = scmPrefixes.filter(function (prefix) {
    return version.indexOf(prefix) === 0
  })
  return !!blacklisted.length
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.david.version.isStable"></a>[function <span class="apidocSignatureSpan">david.version.</span>isStable (version)](#apidoc.element.david.version.isStable)
- description and source-code
```javascript
function isStable(version) {
  return !unstablePattern.test(version || '')
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
