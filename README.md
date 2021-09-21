# lautfm

Nodejs module for Webservice [laut.fm API](http://api.laut.fm)

Details about the API

* <http://api.laut.fm/doc>
* <http://api.laut.fm/documentation/search>

## Install

```
npm install lautfm
```

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
* `searchStations(<params>[, list])` Search stations <http://api.laut.fm/documentation/search>

## Properties
* `station_sections` List of available sections for getStation()
* `stations_by` List of available types for getStations({by: {type}...})

## section

Values used as section parameters in `getStation(<name>[, section])`.

| section      | Description |
| ------------ | ----------- |
| current_song | The currently playing song of a single station. |
| last_songs   | The 10 last songs of a single station. |
| listeners    | The listener count of a single station. |
| next_artists | Next artists of a single station. Information may be inacurate or plainly wrong right before a playlist or schedule change. |
| playlists    | The schedule of a single station grouped by playlists. |
| schedule     | The schedule of a single station. |

## Station by types

Values used as 'by' in filter object used in `getStations()`

| type    | Description |
| ------- | ----------- |
| genre   | All stations of a certain genre. |
| letter  | All stations beginning with the certain letter. |
| live    | A list of all stations sending live at the moment. |
| numbers | All stations beginning with a number. |

## Example

Get all stations starting with letter e

```javascript
let filter = {
  by: 'letter', // filter by letter
  term: 'e'     // stationname starting with 'e'
}
laut.getStations(filter)
  .then(data => console.log(data))
  .catch(err => console.error(err))
```
Result will be a Object like [this](http://api.laut.fm/stations/letter/e)
