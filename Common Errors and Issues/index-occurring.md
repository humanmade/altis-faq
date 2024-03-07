#  ElasticSearch Index: Error: An index is already occurring. Try again later. 

It can be possible that when trying to perform a reindex the flag in-progress flag get stuck, resulting in the following error:
```
Error: An index is already occurring. Try again later.
```
In such a case, you can clear the flag by running the following:
```
wp elasticpress clear-sync 
```
If the above doesn't work, it can also be stuck in a WordPress Transient, so you can then try the following:
```
wp transient delete ep_wpcli_sync --network
```
Occasionally this value can also be stored in the object cache, so flushing the cache with the following command may also be necessary.
```
wp cache flush
```