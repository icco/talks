# Five Minute Cron

Cron is a pretty straight forward concept. Basically it is a list of commands
you want to run at an interval. There are lots of cron files scattered
throughout the system, but for random user tasks, you want to use `crontab`.

`crontab` can be run three ways you really care about: 

 * `crontab -l` : Lists the currently installed crontab
 * `crontab file` : installs a file as the current crontab (OVERWRITES YOUR CURRENT CRONTAB).
 * `crontab -e` : Opens your current crontab in $EDITOR.

That's all fine and dandy, but how do you actually read the output of cron?

    * * * * * your awesome command

So first of all, what's up with those asterisks?

    field          allowed values
    -----          --------------
    minute         0-59
    hour           0-23
    day of month   1-31
    month          1-12 (or names, see below)
    day of week    0-7 (0 or 7 is Sun, or use names)

An asterisk means every value in the allowed values column. You can also do a
range, like `8-10`. Or if you really want to be fancy you can say `*/5`, which
means every five minutes.

Your command is run as your user. Depending on your system, your command may be
run by whatever shell it pleases. To make sure it is running in bash, add the
following to the top of your crontab.

    SHELL=/bin/bash

You can also say where to mail the output of your cron's output to
(historically cron commands don't write anything besides errors to standard
out).

    MAILTO=nwelch@calpoly.edu

## Examples

Clear out the tmp folder in your home directory every Saturday at 4:05am.

    5 4 * * sat rm -rf ~/tmp/*

Write a period to a file 24/7.

    * * * * * echo '.' >> /var/log/period.txt

Every fifteen minutes, between 8pm and 10pm, during the month of February, email my roommates phone.

    */15 20-22 * 2 *  echo 'Dude. It's raining.' | sendmail 7073018294@vtext.com

## Questions?

Check out the following man pages: 

 * cron    (8) - daemon to execute scheduled commands 
 * crontab (1) - maintain crontab files for individual users
 * crontab (5) - tables for driving cron

