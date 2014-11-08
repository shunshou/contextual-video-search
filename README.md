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

* __Free Base Topics__
 * <https://developers.google.com/youtube/v3/docs/search/list#topicId>
 * <https://www.freebase.com/>
 * <http://tesladocet.com/programming/freebase-semantic-web-app-google-semantic-search/>

 ![picture alt](https://raw.githubusercontent.com/shunshou/contextual-video-search/master/web1.JPG "Title is optional")

 ![picture alt](https://raw.githubusercontent.com/shunshou/contextual-video-search/master/web2.JPG "Title is optional")

 * __Youtube Player API__
  * http://css-tricks.com/play-button-youtube-and-vimeo-api/

 * __Node.js__
  * http://howtonode.org/how-to-install-nodejs
  * https://devcenter.heroku.com/articles/getting-started-with-nodejs#deploy-the-app

 * __Node.js Wrappers__
  * https://www.npmjs.org/package/mapbox
  * https://www.npmjs.org/package/node-sass
  * https://www.npmjs.org/package/youtube-api

 * __SASS__
  * http://www.zingdesign.com/the-sass-and-compass-tutorial-for-absolute-beginners/
  * http://compass-style.org/reference/compass/utilities/sprites/
  * http://sass-lang.com/guide
  * http://hugogiraudel.com/2013/08/08/advanced-sass-list-functions/

 * __Github + Getting Started__
  * git remote add origin <github repo>
  * git remote add heroku git@heroku.com:<app name>.git
  * git pull origin master
  * git add filename.xyz
  * git add -A
  * git add . --force
  * git commit -m "message"
  * git push origin master
  * git push heroku master
  * Heroku https://dashboard-next.heroku.com/apps
  * http://nodejs.org/
  * https://devcenter.heroku.com/articles/getting-started-with-nodejs#view-logs

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
* Time difference around the world



 `code()`
