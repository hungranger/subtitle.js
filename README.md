
# subtitle.js

[![Build Status](https://travis-ci.org/gsantiago/subtitle.js.svg?branch=master)](https://travis-ci.org/gsantiago/subtitle.js)
[![Code Climate](https://codeclimate.com/github/gsantiago/subtitle.js/badges/gpa.svg)](https://codeclimate.com/github/gsantiago/subtitle.js)
[![Test Coverage](https://codeclimate.com/github/gsantiago/subtitle.js/badges/coverage.svg)](https://codeclimate.com/github/gsantiago/subtitle.js)
[![npm version](https://badge.fury.io/js/subtitle.svg)](http://badge.fury.io/js/subtitle)

Parse and manipulate SRT (SubRip) format.

## Installing

`npm install subtitle --save`

## Usage

```javascript
var Subtitle = require('subtitle');

var captions = new Subtitle();

captions.parse('your srt here');

console.log(captions.getSubtitles());

```

It's gonna return an array like this:

```javascript
[
  {
    index: 1,
    start: '00:00:20,000',
    end: '00:00:24,400',
    text: 'Bla Bla Bla Bla'
  },
  {
    index: 2,
    start: '00:00:24,600',
    end: '00:00:27,800',
    text: 'Bla Bla Bla Bla'
  }
]
```

You can also pass options to the `getSubtitles()` method.

```javascript
captions.getSubtitles({
  duration: true, // Include the `duration` property
  timeFormat: 'ms' // Set time format to milliseconds
});
```

Here's the result:

```javascript
[
  {
    index: 1,
    start: 20000,
    end: 24400,
    duration: 4400,
    text: 'Bla Bla Bla Bla'
  },
  {
    index: 2,
    start: 24600,
    end: 27800,
    duration: 3200,
    text: 'Bla Bla Bla Bla'
  }
]
```


## Tests

`npm test`

## Roadmap
* [x] Basic SRT parser
* [x] Basic manipulation
* [x] Stringfy
* [x] Time conversion
* [x] Duration property
* [ ] WebVTT support
* [ ] Browser support (including for Browserify)
* [ ] Better docs
