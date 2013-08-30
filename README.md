Pull GCal
=========

Pull GCal is a Python script  used to pull calendar entries from [Google
Calendar][1].   It   can  also   produce  output  formatted   for  Emacs
[Org-Mode][2].

Configuration File
------------------

The    information     used    by    Pull    GCal     is    stored    in
`~/.pull-gcal/pull-gcal.conf`.  This  file consists of  several entries,
each of which has the following structure:

    [Name of the calendar]
    xml=Address of the calendar's feed
    timeout=Minimum time to pass before refresh
            the local copy of the feed (in minutes)

Local Copies of Feeds
---------------------

Pull GCal does not download the feeds every time it is called.  Instead,
it saves local copies of the feeds in `~/.pull-gcal/` and refreshes them
only after a certain amount of  time specified in the configuration file
has passed.  The local copies are  named after the calendars' names with
the file extension `.xml`.

Usage
-----

Usage of the script  is very simple.  Just set the  execute bit and then
run the script.  The Org-Mode entries  will be sent to stdout, which you
can redirect  to anywhere.  To  automate this  procedure, you can  add a
line in your crontab, for example:

    @hourly /usr/local/bin/pull-gcal >~/todo/gcal.org


[1]: https://www.google.com/calendar/
[2]: http://orgmode.org/
