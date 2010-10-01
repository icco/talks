# Five Minute Cron

Cron is a pretty straight forward concept. Basically it is a list of commands
you want to run at an interval. There are lots of cron files scattered
throughout the system, but for random user tasks, you want to use `crontab`.

    field          allowed values
    -----          --------------
    minute         0-59
    hour           0-23
    day of month   1-31
    month          1-12 (or names, see below)
    day of week    0-7 (0 or 7 is Sun, or use names)

