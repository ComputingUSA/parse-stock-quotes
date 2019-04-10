#!/bin/sh
PQLOGFILE=/dev/null
CSVFILE=pq.csv
AWKFILE=pqfilter.awk

date >> $PQLOGFILE
/home/ungsun_p/oper/pq/DLquot >> $PQLOGFILE
cat $CSVFILE |grep -v Connection|grep -v GET|awk 'BEGIN { FS = "," }
{ print $1 " " $2 " " $5 " " $4}
END { print "ENDOFFILE" }' |sed "s/\"//g"|sed "s/PM/P/g"|grep -v ENDOFFILE|mail page_peter_ungsunan@ins.com
#cp $CSVFILE thecsvfile
rm $CSVFILE
