# proj6-Gcal
Snarf appointment data from a selection of a user's Google calendars 

## User
The application is fairly simple - provided the necessary secrets to
access a user's Google calendars, the site returns times when that user
is busy based on the dates, times, and selected calendars provided by the
client.

## Running the program
After forking and cloning the repository, you should be able to run 
the program with the following commands:
* bash ./configure
* make run
Alternatively, you should be able to deploy through gunicorn by using 
'make service' instead.

## FIXME
* The server currently relies on its own local timezone when it should be
drawn from the client.
* There is a timestamp issue with far-future dates when using arrow. A workaround
is in place, but it needs to be corrected once arrow has been patched. See the
flask_main.py interpret_time() function for more detail.