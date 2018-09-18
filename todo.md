## Reset the cron job for shutdown

```
#Computer shutdown/wake
30 20 * * * /usr/local/bin/shutwake
```

## shutwake script:

```
#!/bin/bash
sh -c "echo 0 > /sys/class/rtc/rtc0/wakealarm"
sh -c "echo `date '+%s' -d '+2 minutes'` > /sys/class/rtc/rtc0/wakealarm"
shutdown -h now

```
