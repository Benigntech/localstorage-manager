Localstorage Manager Library
==================================

An extremely lightweight time difference javascript library.

## Install
```$xslt
// npm
npm i js-localstorage-manager

// yarn
yarn add js-localstorage-manager
```
## Usages

##### Use in HTML
```html
<script type="text/JavaScript" src="dist/localstorage-manager.min.js" />

//use global class LocalStorageCache
```
##### Or use in javascript
```js
// es6 or higher
import LocalStorageCache from 'js-localstorage-manager';

// es5
var LocalStorageCache = require('js-time-diff');
```

## Example
```js
/**
* with default cache name "ls-cache"
* @type {LocalStorageCache}
*/
const localStorageCache = new LocalStorageCache();

/**
* with custom cache name
* @type {LocalStorageCache}
*/
const localStorageCache = new LocalStorageCache("YOUR_CUSTOM_CLASSNAME");

/**
* create cache with username or user id for store user specific data
* @type {LocalStorageCache}
*/
const localStorageCache = new LocalStorageCache("YOUR_CUSTOM_CLASSNAME", "USER_NAME");

/**
* get current user's cache
* @type {*|{}}
*/
const userCache = localStorageCache.cache;

/**
* get all user's cache
* @type {any|{}}
*/
const allUsersCache = localStorageCache.allCache;

/**
* get local storage cache name
* @type {string|*}
*/
const name = localStorageCache.cacheName;

/**
* get current username
* @type {string}
*/
const userName = localStorageCache.userName;

/**
* get cache by cache name
* @type {any|{}|null}
*/
const customCache = localStorageCache.getCache("CACHE_NAME");

/**
* open a cache by cache name
* @type {CacheManager}
*/
const cache = localStorageCache.open("CACHE_NAME");

/**
* get cache name
* @type {string}
*/
const cacheName = cache.name;

/**
* get all cached data
* @type {*|{}}
*/
const cacheData = cache.result;

// put your data to cache
cache.put("NAME", {"YOUR_CUSTOM_DATA"});

/**
* get your cached data by name
* @type {{}|null}
*/
const data = cache.get("NAME");

// clear your cached data
cache.clear();

// update/sync your data
cache.update();

// delete your cached data by name
cache.delete("NAME");

/**
* get last update time different
* @type {{secondsAgo: number, minutesAgo: number, hoursAgo: number, daysAgo: number, monthsAgo: number, yearsAgo: number}}
*/
const timeDiff = cache.timeDiff("NAME");

```