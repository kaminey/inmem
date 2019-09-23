# inmem
A simple in memory key value database.

## Should support following operations.
```
   1.  SHOW DBS - to show all the databases associated with the instance.
   2.  CREATE DB <dbname> - To create a database.
   3.  SELECT DB <dbname> - To select a given database.
   4.  SET <key> <val> <exp|optional> - add a given key to the select db.
   5.  INCRBY <key> <counter> - increment key value by counter. If key does not exists, fail operation.
   6.  DECRBY <key> <counter> - decrement key value by counter. if key does not exists , fail operation.
   7.  EXISTS <key> - return true if key exists, false otherwise.
   8.  GET <key> - fetch the value of the provided key.
   9.  DEL <key> - delete a given key from the database.
   10. EXP <key> <exp> - expires the given key at exp seconds from now.
   11. SUBSCRIBE <channel> - subscribe to the following channel [channel will be created on call to subscribe].
   12. PUBLISH <channel> <msg> - publish the given message to the channel.
```
  
## Should be thread safe and support concurrent operations.
   We can either choose the redis way of handling thread safety (single threaded), or locking the operation at the key level.
  
## Should persist to hdd (configuration)
      hdd_persist <true|false> - if true data will be flushed to hdd every <hdd_persist_freq> seconds.
      hdd_persist_freq <time> - Data will be flushed to hdd every <hdd_persist_freq> seconds.
