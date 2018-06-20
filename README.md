# abrequire
A-B-Require is pretty require with absolute path. Simply Easy Smaller < 1Kb

## Problem
When the directory structure of your Node.js application (not library!) has some depth, you end up with a lot of annoying relative paths in your require calls like:
```javascript
const mysql = require('../../../../db/mysql')
```
Those suck for maintenance and they're ugly. [link](https://gist.github.com/branneman/8048520)
## Install
```javascript
npm install abrequire --save
```

## How to use
```javascript
global.use = require('abrequire')
```
or
```javascript
const use = require('abrequire')
```

## Example
```
-root
--app
----db
------mysql.js
------mongoose.js
----routes
------group
---------subGroup
------------router.js
--server.js
--node_module
--package.json
```
When `router.js` require `mysql.js`  relative path
```javascript
const mysql = require('../../../../db/mysql')
```
When `router.js` require `mysql.js`  absolute path
```javascript
const use = require('abrequire')
const mysql = use('app/db/mysql')
```
## Authors

* **Nonthachai Korninai** - [Github](https://github.com/7elven)

## License

This project is licensed under the MIT License

