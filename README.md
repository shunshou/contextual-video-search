contextual-video-search
=======================

# Application Concept #

Contextual live? (Youtube) video search with world map (time/location/"trending")

* https://projects.invisionapp.com/share/PG1MDIFF9

----

# Inspirations/Tutorials #

* __Geocoding__
 * <https://developers.google.com/maps/documentation/javascript/geocoding>
 * <https://www.mapbox.com/developers/api/geocoding/>
 * https://github.com/youtube/geo-search-tool

* __ Free Base Topics__
 * <https://developers.google.com/youtube/v3/docs/search/list#topicId>
 * <https://www.freebase.com/>
 * <http://tesladocet.com/programming/freebase-semantic-web-app-google-semantic-search/>

 ![picture alt](http://www.brightlightpictures.com/assets/images/portfolio/thethaw_header.jpg "Title is optional")

 * __ Youtube Player API __
  * http://css-tricks.com/play-button-youtube-and-vimeo-api/

 * __ Node.js __
  * http://howtonode.org/how-to-install-nodejs
  * https://devcenter.heroku.com/articles/getting-started-with-nodejs#deploy-the-app

 * __ Node.js Wrappers __
  * https://www.npmjs.org/package/mapbox
  * https://www.npmjs.org/package/node-sass
  * https://www.npmjs.org/package/youtube-api

 * __ SASS __
  * http://www.zingdesign.com/the-sass-and-compass-tutorial-for-absolute-beginners/
  * http://compass-style.org/reference/compass/utilities/sprites/
  * http://sass-lang.com/guide
  * http://hugogiraudel.com/2013/08/08/advanced-sass-list-functions/

 * __ Github + Getting Started __
  * git remote add origin <github repo>
  * git remote add heroku git@heroku.com:<app name>.git
  * git pull origin master
  * git add filename.xyz
  * git commit -m "message"
  * git push origin master
  * git push heroku master
  * Heroku https://dashboard-next.heroku.com/apps
  * http://nodejs.org/

# UI Notes #

* Color schemes (need to look good): Adobe Kuler https://color.adobe.com/
* FontAwesome for “Web 2.0” fonts
* Reference: http://quizlet.com/ map
* Rashomon style video http://rieff.ieor.berkeley.edu/rashomon/
* Stream video from Youtube (or alternatively, Twitch supports real time streaming; if no real time streaming, check out vid.me for anonymous videos)
* Use Mapbox for maps (zoom, heat map, hot spots)
 * https://www.mapbox.com/tilemill/docs/manual/interface-tour/ 
 * https://www.mapbox.com/blog/mapbox-fusion-tables-drones/
* Otherwise, possibly Google Maps API is good enough
 * http://snazzymaps.com/?page=3 custom designs
 * http://rastrack.co.uk/ Raspberry Pi tracker
* Larger spots → more streams (front); different colors correspond to different event start time
 * Only up to 24 hours on live map (?)
* Zoom in max: hot spots grouped by City + Hashtag + Day
* Hovering over hot spots causes them to glow
* Display up to 5 videos simultaneously (drag + drop)
* Search can be City, Hashtag, Date, etc. -- no order required, comma separated, hashtag requires # in query
* Best way to store/display real-time geo data; access MySQL database to update hot spots on the fly?
* Android: use Youtube Livestream API to setup Livestream (instead of manually doing it now)
 * Already signed into Google?
* Display streams based off of # of views + # of streams @ event (for search)
* Secret pi stream identifier (for sending video through 1 out of many phones)
* When stream starts, add to group {city+hashtag+date}
 * Field: Time_start
 * Field: Time_stop (blank until exits)
 * Sort by earliest start time

# To Do 11/7/14 #

* Youtube Livestream
* Mapbox
* Datapacket {#+City+Date; Timestamps, GPS, Compass} + Video & Audio to Youtube
* Bird-eye vew w/ playback
* Choose from most viewed/time/location
* Focus on Livestream
 * Click map hotspot
 * Track route w/ compass direction (top street map)
 * Timeline/playback timeline
 * Videos
* Can change "day" associated w/ map



 `code()`
