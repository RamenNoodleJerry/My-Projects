Using the Google Places API with a Database and
Visualizing Data on Google Map

In this project, we are using the Google geocoding API
to clean up some user-entered geographic locations of
university names and then placing the data on a Google
Map.

The first problem to solve is that the Google geocoding
API is rate limited to a fixed number of requests per day.
So if you have a lot of data you might need to stop and
restart the lookup process several times.  So we break
the problem into two phases.

In the first phase we take our input data in the file
(where.data) and read it one line at a time, and retrieve the
geocoded response and store it in a database (geodata.sqlite).
Before we use the geocoding API, we simply check to see if
we already have the data for that particular line of input.

Run the geoload.py program. This program will read the input
lines in where.data and for each line check to see if it is already
in the database and if we don't have the data for the location,
call the geocoding API to retrieve the data and store it in
the database.

The program scans to the point where it finds un-retrieved
locations and starts retrieving them.

Once you have some data loaded into geodata.sqlite, you can
visualize the data using the (geodump.py) program. This
program reads the database and writes tile file (where.js)
with the location, latitude, and longitude in the form of
executable JavaScript code.

Simply open where.html in a browser to see the locations.  You
can hover over each map pin to find the location that the
geocoding API returned for the user-entered input.  If you
cannot see any data when you open the where.html file, you might
want to check the JavaScript or developer console for your browser.

