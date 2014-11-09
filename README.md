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
* Refresh map every minute

# Node.js + Heroku Tutorials #

* http://qiita.com/ta9to/items/3cf49726b9636c8f0c0c

# Heroku Specific #

* git init
* .gitignore --> directory name
* git add .
* git commit -m "test"
* heroku create
* git push heroku master
* heroku open
* Procfile starts application specified (web: node app.js)
* Can run locally via node app.js

# Server Stuff #

* Post to server -- packet from Pi
* Heroku reads + updates database
* Post to server for web forms - server takes action
* Identify Pi/Form posts, unique ID
* Dynamic DNS?
* What is GET for?
* Direct write to SQL or need to go through POST on nodejs side?
 * Need to go through POST, b/c otherwise SQL database info is embedded into app (not safe)
* Youtube is pure JS
* https://wiki.postgresql.org/wiki/Grouping_Sets

# Pi Web Socket $

* http://www.jaredwolff.com/blog/raspberry-pi-getting-interactive-with-your-server-using-websockets/
* http://www.raspberrypi.org/forums/viewtopic.php?f=28&t=75037
* web browser only
* server.js; index.html; package.json (needed for node.js to specify dependencies)
* npm install
* Procfile contains server process needed to get running
* foreman start
* listening @ localhost:5000
* git init
* git add .
* git commit -m "msg"
* heroku create
* heroku config (check)
* heroku addons:add heroku-postgresql:hobby-dev
* git push heroku master
* heroku open
* can include node_modules in .gitignore 
* heroku pg:psql
* create table post(body text); ---- create table table_name(field field_type, field field_type); -- integer, text, etc. 
* insert into post values ('hello');
* \q

= Google Talk =
* Alternatives: Twitter
* http://solvingmytechworld.blogspot.com/2013/01/gtalk-notifications-from-raspberry-pi.html
* http://www.raspberrypi.org/forums/viewtopic.php?f=29&t=44783

= RTMP Android = 
* http://stackoverflow.com/questions/15571571/how-to-stream-rtmp-live-video-in-android

= Pi Dynamic DNS =
* http://www.element14.com/community/community/raspberry-pi/blog/2012/07/26/dynamic-dns--open-up-your-pis-webserver-to-the-world

= Data structure = 

* Number of views
* City + Date + Hashtag
* Timestamp + GPS + Compass
* Unique ID -- when DL android app, should give unique ID of app or stream?
* Youtube URL + viewer count

* When you hit GO, increments view count; MAC address as ID? 

INSERT INTO films (code, title, did, date_prod, kind) VALUES
    ('B6717', 'Tampopo', 110, '1985-02-10', 'Comedy'),
    ('HG120', 'The Dinner Game', 140, DEFAULT, 'Comedy');

* https://wiki.postgresql.org/wiki/Grouping_Sets

temp database storage after initial query?? sub table w/ more data? 

<postgres=# SELECT name, place, SUM(count) FROM cars GROUP BY GROUPING SETS(name, place, ());




group by date + hashtag + city --> number and earliest 

update map every minute? 


id

----


refresh page
group by {city + date + hashtag}
  get count(sum)
  earliest time stamp (earliest function?)
  http://www.postgresql.org/docs/9.3/static/queries-table-expressions.html
when click on hotspot
  make new table based off of group by
  http://www.postgresql.org/docs/8.3/static/sql-createtableas.html

android sends request for all hashtags from today at specific location for auto complete
  get request --> server pulls info from database
  --> sends back to android (how??)
  http://www.basic4ppc.com/android/forum/threads/connect-android-to-mysql-database-tutorial.8339/
  http://stackoverflow.com/questions/25638606/node-js-server-mobile-client
  http://fahmirahman.wordpress.com/2011/04/21/connection-between-php-server-and-android-client-using-http-and-json/

update array based off of FIND unique stream ID + append to array
http://www.postgresql.org/docs/9.1/static/arrays.html
http://www.postgresql.org/docs/9.1/static/functions-array.html

need to pull next stream ID from database (GET request from Android)

make local database
make database with tables, subtables? based off of current data structure
add fake data
remotely add data (pi or from local)
display data + auto update each time remotely added (maybe not separate data query but locally add for view update)
search feature to group + display as group 
sub search : display as more group (sub table?) - 5 min increments/location
on video display: increment viewer count (or figure out how to use Youtube)
Youtube Javascript API -- pull stored video from search query, control playback time
Mapbox API -- how to redisplay info; how to make GPS --> city

HW:
pi send Gchat or Twitter + send put request to database
pi uploads rtmp to youtube livestream (or local?) 
you stare at youtube, see person; can change lock/unlock option --> push back to pi

http://thefloppydisk.wordpress.com/2013/05/08/how-to-build-a-restful-web-api-on-a-raspberry-pi-in-javascript/

* https://developers.google.com/youtube/js_api_reference

 `code()`


 psql -h localhost
 CREATE DATABASE dbname;
CREATE TABLE post(body text);
export DATABASE_URL=postgres:///$(whoami)

\list -- lists all databases
\dt lists all tables in current database
\c database_name -- connect to certain db

DROP DATABASE db_name

SELECT * FROM post;
insert into post values ('hello');
SELECT * FROM post;

---



