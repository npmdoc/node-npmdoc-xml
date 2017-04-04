# api documentation for  [xml (v1.0.1)](http://github.com/dylang/node-xml)  [![npm package](https://img.shields.io/npm/v/npmdoc-xml.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-xml) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-xml.svg)](https://travis-ci.org/npmdoc/node-npmdoc-xml)
#### Fast and simple xml generator. Supports attributes, CDATA, etc. Includes tests and examples.

[![NPM](https://nodei.co/npm/xml.png?downloads=true)](https://www.npmjs.com/package/xml)

[![apidoc](https://npmdoc.github.io/node-npmdoc-xml/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-xml_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-xml/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-xml/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-xml/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Dylan Greene",
        "url": "https://github.com/dylang"
    },
    "bugs": {
        "url": "http://github.com/dylang/node-xml/issues"
    },
    "contributors": [
        {
            "name": "Dylan Greene",
            "url": "https://github.com/dylang"
        },
        {
            "name": "Dodo",
            "url": "https://github.com/dodo"
        },
        {
            "name": "Felix Geisendrfer",
            "url": "felix@debuggable.com"
        },
        {
            "name": "Mithgol"
        },
        {
            "name": "carolineBda",
            "url": "https://github.com/carolineBda"
        },
        {
            "name": "Eric Vantillard https://github.com/evantill"
        },
        {
            "name": "Sean Dwyer https://github.com/reywood"
        }
    ],
    "dependencies": {},
    "description": "Fast and simple xml generator. Supports attributes, CDATA, etc. Includes tests and examples.",
    "devDependencies": {
        "ava": "^0.11.0"
    },
    "directories": {},
    "dist": {
        "shasum": "78ba72020029c5bc87b8a81a3cfcd74b4a2fc1e5",
        "tarball": "https://registry.npmjs.org/xml/-/xml-1.0.1.tgz"
    },
    "gitHead": "c03b84bc1da9251f04db65428c8c341e51d0ff72",
    "homepage": "http://github.com/dylang/node-xml",
    "keywords": [
        "xml",
        "create",
        "builder",
        "json",
        "simple"
    ],
    "license": "MIT",
    "main": "lib/xml.js",
    "maintainers": [
        {
            "name": "dylang",
            "email": "dylang@gmail.com"
        },
        {
            "name": "erisds",
            "email": "erisds@gmail.com"
        }
    ],
    "name": "xml",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+ssh://git@github.com/dylang/node-xml.git"
    },
    "scripts": {
        "test": "ava"
    },
    "version": "1.0.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module xml](#apidoc.module.xml)
1.  [function <span class="apidocSignatureSpan">xml.</span>Element ()](#apidoc.element.xml.Element)
1.  [function <span class="apidocSignatureSpan">xml.</span>element ()](#apidoc.element.xml.element)



# <a name="apidoc.module.xml"></a>[module xml](#apidoc.module.xml)

#### <a name="apidoc.element.xml.Element"></a>[function <span class="apidocSignatureSpan">xml.</span>Element ()](#apidoc.element.xml.Element)
- description and source-code
```javascript
function element() {
    var input = Array.prototype.slice.call(arguments),
        self = {
            _elem:  resolve(input)
        };

    self.push = function (input) {
        if (!this.append) {
            throw new Error("not assigned to a parent!");
        }
        var that = this;
        var indent = this._elem.indent;
        format(this.append, resolve(
            input, indent, this._elem.icount + (indent ? 1 : 0)),
            function () { that.append(true) });
    };

    self.close = function (input) {
        if (input !== undefined) {
            this.push(input);
        }
        if (this.end) {
            this.end();
        }
    };

    return self;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.xml.element"></a>[function <span class="apidocSignatureSpan">xml.</span>element ()](#apidoc.element.xml.element)
- description and source-code
```javascript
function element() {
    var input = Array.prototype.slice.call(arguments),
        self = {
            _elem:  resolve(input)
        };

    self.push = function (input) {
        if (!this.append) {
            throw new Error("not assigned to a parent!");
        }
        var that = this;
        var indent = this._elem.indent;
        format(this.append, resolve(
            input, indent, this._elem.icount + (indent ? 1 : 0)),
            function () { that.append(true) });
    };

    self.close = function (input) {
        if (input !== undefined) {
            this.push(input);
        }
        if (this.end) {
            this.end();
        }
    };

    return self;
}
```
- example usage
```shell
...
 For example you can use ''\t'' for tab character, or ''  '' for two-space tabs.

'stream' Return the result as a 'stream'.

**Stream Example**

'''js
var elem = xml.element({ _attr: { decade: '80s', locale: 'US'} });
var stream = xml({ toys: elem }, { stream: true });
stream.on('data', function (chunk) {console.log("data:", chunk)});
elem.push({ toy: 'Transformers' });
elem.push({ toy: 'GI Joe' });
elem.push({ toy: [{name:'He-man'}] });
elem.close();
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
