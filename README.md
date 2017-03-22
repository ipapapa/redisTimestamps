# Introduction
This is a modified Redis 3.0.4 version that will be used as the basis for Dynomite data reconciliation feature. There are several added components in Redis.
For simplicity we call it Redis 3.0.5.

## Status
Experimental

## New Redis API
* GETTIME key : returns the last time the value of that key was created or modified.
* HGETTIME myhash field : returns the last time the value in "field" of the hash "myhash" was created or modified. 
* SMEMBERSTIME myset : return the value and timestamp of each object in the set "myset".
* COMPAREANDSET key newValue oldValue: Compares if the oldValue is the same as the one in Redis and updates it to the newValue. If the oldValue is different then it just returns OK.
* COMPAREANDDEL key oldValue: Compares if the oldValue is the same as the one in Redis and deletes it.
* HCOMPAREANDSET key field newValue oldValue: Performs the same as the COMPARESET but in a field of HASH MAP.
* HCOMPAREANDDEL key field oldValue: Performs the same as the COMPARESET but in a field of HASH MAP.
* SCOMPAREANDSET key newValue oldValue: Performs the same as the COMPARESET in a field of a SET.

## Redis Append of File
* AOF prints the timestamps of every value as follows #XXX.
* AOF prints the timestamp on when the DB was initially first written #XXX.
* BWREWRITEAOF re-writes the AOF with the timestamps from each value.

# Contact 
This is repository is maintained by Ioannis Papapanagiotou
