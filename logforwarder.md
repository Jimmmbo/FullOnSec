# This bash script is trying to simulate Events Per Second to calculate the cost of this load in a cloud environment over a
# 24h period. Unfortunately this does not work well with NC as it sees this as 1 big stream. This is why the sleep is 
# incorporated in the bash script and the '-w3' in Netcat to try and manipulate the script to send 100 logs per second
# This script will be improved over time if I think about it and find a better solution. 

#!/bin/bash

# line increment
inc=50

# total number of lines in the file
total=$(wc -l logfile | awk {'print $1'})

while [ 1=1 ]
do
for ((i=1;i<total;i=i+inc)); do
   sed -n "$i,$((i+inc-1))p" logfile
   sleep 1s
   #this is done to simulate EPS
done
done

# Run this in the commandline

./filename.sh | pv -s600 --line-mode | nc -w3 ip.ad.dr.ess port number
