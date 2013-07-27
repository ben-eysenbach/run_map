run_map
=======

Automatically plans a running loop of a given distance.

![Alt text](/path/to/img.jpg "Screenshot")

How it Works:
---------
It picks a point roughly a third of the total distance away from the starting point, and then picks another point the same distance from the starting point, but rotated roughly 60 degrees clockwise.  It then uses the Google Maps API (JS v3) to plan a route through these three points (two waypoints and the starting point).  If the given route is too short or too long, new points are chosen.  This is a good approximation of the final route.  However, this approximate route often includes annoying detours near the waypoints.  To get rid of these, it then looks at the route near the waypoints and 'backtracks' along any leg shorter than a certain distance.  There's also a check to ensure that the path is a loop, and not just and 'out-and-back' run.  This process is repeated until a good route is found.

Technicalities:
---------
The distance to the waypoints is actually calculated using trig functions, and then multiplied by a scaling factor less than one to account for the fact that the running path is going to be longer than the strait-line path.  Once the distance has been calculated, the lat/log points is found using trig and the Pythagorean Theorem (under the assumption that the world is flat).

If the route returned by Google is too long or too short, the tolerance is increased before remapping, to ensure that a valid route will eventually be returned.

There's also a counter the decrements for each rerouting.  Sometimes in rural areas there are no valid routes with no U-turns, so U-turns are allowed after the counter reaches zero.
