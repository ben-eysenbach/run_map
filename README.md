Run Map
------------
Automatically generate running loops!

![screenshot](https://raw.github.com/ben-eysenbach/run_map/master/Screenshot.png)

Details:
After calculating youre LatLong position, it finds a point 1/3 of your run-length away from you.
Then it plots another point 60 degress to either side, and finally connects the three points to complete your run.

The angle between legs 1 and 3, set to 60 degrees above, can be changed using the "angle" form.
The legs of your run will lengthen/shorten a cooresponding amount(Trig!).

The first few routes shown are often rejected because they are too short or too long.
As more routes are generated, the "tolerance" for error increases, so you'll always get a route, even it
if is a too long or too short.

I've also added some checks against dead-end routes.  I get directions to the exact position of the waypoints
and then move the waypoints a few steps earlier in the route.


Please fork or email suggestions!
