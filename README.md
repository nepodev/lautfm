# lautfm

Nodejs module for Webservice [laut.fm API](http://api.laut.fm)

## Usage

```javascript
const Lautfm = require('lautfm')

const laut = new Lautfm();

laut.searchStations({query: 'ska', limit: 2})
    .then(data => console.log(data))
    .catch(err => console.error(err))
```

## Methods

TODO
