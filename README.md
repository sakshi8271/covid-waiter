# Covid19 Waiter

This project aims to avoid the gatherings of people in various supermarkets and pharmacies during the covid-19 pandemic. Based on the geolocation of the device, it will show various points of interest such as supermarkets, pharmacies, clinics, bars etc., with an estimate waiting time and a forecast of the next hour.

**NOTE**: This project does not wanna be for commercial use. This project wants to help people to stay outside their house as little time as possible and to avoid other people for the quarantine period.

![snippet](https://tkganesh.me/covid-waiter/assets/map.png)


# How it works

The Front-end side is super simple and uses Open Street Map with the Leaflet.js library.

It uses also geocode.xyz API, client side, to retrieve details about the address and the city from the geo-coordinates retrieve by the HTML5 API.

The Back-end is powered by Flask, a micro-framework for building some simple APIs to retrieve data from Google Places and [HERE Places API](https://developer.here.com/documentation/places/dev_guide/topics/quick-start-find-text-string.html) for getting Places by Category like (Supermarket, pharmacies etc).

**NOTE**: this project does not use the official Google APIs, but it is working via a sort of workaround / bug. We can call this "scraping", but it is not the right word.

# Data

The data comes from Google, like Traffic for Maps, in real time. The data are also based on the data of the past week, to have a history (Google based), the time spent inside a place and the estimated waiting time to be able to complete the purchase.

The waiting time is also based on the current popularity (readme as realtime) of a specific place. This feature is not available for all places, but for the vast majority it is. In this way, the estimated waiting times can still be reliable, since the calculations that are carried out on these data try to take into consideration the variables of the emergence such as social distancing, less influx of people in closed places etc.
The data is then divided into hours and weekdays.

In the future it will then perhaps be possible to give an estimate on the following hours.

![snippet](https://coderganesh.github.io/covid-waiter/assets/map2.png)

**All times are to be kept as estimates.**

In fact, the same data that you would view on Google are used, i.e. the data within the local business.

Please, note that sometimes a place can have a parking area or other stuff where the geolocation can make some mistakes. I can not detect where the people are, if they are people or car, how many people are in the line etc etc. The estimates are based on the data that come from Google with an additional formula to get an approx time to wait. This error can change from a place to another.


# TODO

- Add search input in an overlay
- Get geoip information to searh place in region **in progress**
- Add a sidebar to list all the visible places **testing**
- Add autosuggest on search city/address **in progress**
- Add geocoding data from geocode API in client localStorage as a cache **in progress**
- Add history
- Need to optimize the load avg to grant the access to 1500 users in 10min **testing**
- Add category filters and force estimation
- Refacotring UI/UX #9 **in progress**
- add favorites location
- Change modal asking the geodata/search
- guarantee accessibility


# Credits

- The waitingtimes lib is based on the [populartimes python library](https://github.com/m-wrzr/populartimes/).
- The geolocation client utility comes from the [greg's repo](https://github.com/gregsramblings/getAccurateCurrentPosition).
- The Places with category comes from [HERE places API](https://developer.here.com/documentation/places/dev_guide/topics/quick-start-find-text-string.html).
- The geolocation API used on the backend site is provided from [ArcGIS](https://developers.arcgis.com/).

Cheers.
