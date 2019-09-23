# inmem
A simple in memory key value database.

## Should support following operations.
   1.  SHOW DBS - to show all the databases associated with the instance.
   2.  CREATE DB <dbname> - To create a database.
   3.  SELECT DB <dbname> - To select a given database.
   4.  SET <key> <val> <exp|optional> - add a given key to the select db.
   5.  GET <key> - fetch the value of the provided key.
   6.  DEL <key> - delete a given key from the database.
   7.  EXP <key> <exp> - expires the given key at exp seconds from now.
   8.  SUBSCRIBE <channel> - subscribe to the following channel [channel will be created on call to subscribe].
   9.  PUBLISH <channel> <msg> - publish the given message to the channel.
  
## Should be thread safe and support concurrent operations.
   <p>
   We can either choose the redis way of handling thread safety (single threaded), or locking the operation at the key level.
   </p>
  
## Should persist to hdd
      hdd_persist <true|false> - if true data will be flushed to hdd every <hdd_persist_freq> seconds.
      hdd_persist_freq <time> - Data will be flushed to hdd every <hdd_persist_freq> seconds.
