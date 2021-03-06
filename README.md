AccuWeather API wrapper for nodeJS
==============================

[![Build Status](https://travis-ci.org/VBIralo/accuweather.svg?branch=master)](https://travis-ci.org/VBIralo/accuweather)

[![NPM](https://nodei.co/npm/accuweather.png?downloadRank=true&stars=true)](https://nodei.co/npm/accuweather/)

The development of this module is at the earliest stage.


About
-----

A Node.js module for integrating with the [AccuWeather](http://accuweather.com) API. You must acquire an API key to use it.


Installation
------------

The project is hosted on npm

    npm install accuweather

Usage
-----

Create a client and then call one of the exposed methods. See the 
AccuWeather [API](http://apidev.accuweather.com/developers/) for details.

```javascript
const AccuWeather = require('accuweather')
const forecast = new AccuWeather('accukey') //Unique client code used for identification and authorization purposes. Contact AccuWeather to receive an API key.
  
forecast
				.localkey(28580)				// http://apidev.accuweather.com/developers/locationsAPIguide
				.time('hourly/1hour')				// http://apidev.accuweather.com/developers/forecastsAPIguide
				.language("ru")					// http://apidev.accuweather.com/developers/languages
				.metric(true)					// Boolean value (true or false) that specifies to return the data in either metric (=true) or imperial units 
				.details(true)					// Boolean value (true or false) that specifies whether or not to include a truncated version of the forecasts object or the full object (details = true)
				.get()
				.then(res => {
					console.log(res)
				})
				.catch(err => {
					console.log(err)
				})
```

Copyright
---------

Copyright (c) 2017 Vlad Biralo. See LICENSE for further details.
