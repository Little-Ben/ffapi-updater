# ffapi-updater
ffapi-updater helps to manage your Freifunk API file.

## Prerequisites
The following files should be available on filesystem of server (if necessary 
download them before execution, e.g. using wget):
- nodes.json (v2) of Meshviewer's ffmap-backend
- Freifunk-API json file 

ffapi-updater modifies your API file, so best practice is to run it on that 
server that hosts your API file. If this is not possible, you need to 
upload your API file after each execution to its place. In our case API and
map files are hosted on the same server, so both needed json files could be 
referenced directly.

## Installation
To use it, simply clone this repository to a folder on your map server and 
change variables given in configuration part of ffapi-updater.py.

Updating your API file should happen on a regularly basis e.g. each 5 min, 
therefore create a cron job like this: 

<pre>
*/5 * * * * (cd /home/freifunk/ffapi-updater && /usr/bin/python3 /home/freifunk/ffapi-updater/ffapi-updater.py >/home/freifunk/ffapi-updater/ffapi-updater.log 2>&1)
</pre>

## Dependencies
- python3

