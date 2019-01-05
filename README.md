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

* `getGenres()` All available genres. 
* `getStation(<name>[, section])` Get Station details.
* `getStations([filter])` Get a list of stations
* `getServerTime()` The server time
* `getServerStatus()` The current server status and a message.
* `getGenres([list])` All available genres
* `getLetters()` All available starting-letters of the stations.
* `getStationNames()` The names of all stations.
* `getListeners()` The listeners of all stations.
* `getTeaser()` The image sizes are 240x100, 220x220 and 720x300 pixels

## Properties
* `station_sectons` List of available sections for getStation()
* `stations_by` List of available types for getStations({by: {station_by}...})

