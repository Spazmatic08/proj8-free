# proj8-free
Snarf appointment data from a selection of a user's Google calendars 

## User
The application is fairly simple - provided the necessary secrets to
access a user's Google calendars, the site returns times when that user
is busy or available based on the dates, times, and selected calendars 
provided by the client.

## Running the program
After forking and cloning the repository, you should be able to run 
the program with the following commands:
* bash ./configure
* make run
Alternatively, you should be able to deploy through gunicorn by using 
'make service' instead.

The server runs on port 5000 under most circumstances (if deploying on the UO's
ix server, it tries to run on port 7520). You will need to provide the necessary
secrets files yourself - it uses oauth2 and the Google calendars API. 

## FIXME
* The server currently relies on its own local timezone when it should be
drawn from the client.
* Some of the entries in the 'busy' and 'avbl' session variables are showing up
with a timezone value of 'Z' instead of the actual timezone offset. It's not
causing problems yet, but it's worth checking out.
* There is a timestamp issue with far-future dates when using arrow. A workaround
is in place, but it needs to be corrected once arrow has been patched. See the
flask_main.py interpret_time() function for more detail.

## Contact Details
If you need to reach me, you can do so through my email at adibb@cs.uoregon.edu .
Alternatively, the skeleton code was produced by the UO at time of writing. 
If you have questions regarding the core parts of the code, you could 
check for the relevant contact details at the CIS 322 account on github instead.