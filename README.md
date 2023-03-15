# AzRedis-NetworkPerf-Metrics-Monitoring-Bandwidth
AzRedis-NetworkPerf-Metrics-Monitoring-Bandwidth

Network Bandwidth
If the Redis server exceeds the available bandwidth, clients requests could time out because the server can't push data to the client fast enough. Check "Cache Read" and "Cache Write" metrics to see how much server-side bandwidth is being used. 

If your Redis server is exceeding available network bandwidth, you should consider scaling up to a larger cache size with higher network bandwidth.
For more information on network available bandwidth by cache size, see Azure Cache for Redis planning FAQs

src: Redis - Network monitoring
https://learn.microsoft.com/en-us/azure/azure-cache-for-redis/cache-how-to-scale?WT.mc_id=wwc-aces
https://learn.microsoft.com/en-us/azure/azure-cache-for-redis/cache-how-to-monitor#create-alerts


<img width="640" alt="4" src="https://user-images.githubusercontent.com/61469290/225243289-82166899-1ee0-4ba7-813d-41025df1721d.png">

<img width="663" alt="1" src="https://user-images.githubusercontent.com/61469290/225243190-41732753-f84b-428a-aecd-9c0b7a73f4aa.png">

<img width="784" alt="2" src="https://user-images.githubusercontent.com/61469290/225243221-4c5dd794-42c0-4cc0-bbf3-e8ff9a08a285.png">

<img width="807" alt="3" src="https://user-images.githubusercontent.com/61469290/225243255-f8191704-cc84-49cd-9776-0424f07f1da7.png">


List of metrics
Cache Latency (preview)
The latency of the cache calculated using the internode latency of the cache. This metric is measured in microseconds, and has three dimensions: Avg, Min, and Max. The dimensions represent the average, minimum, and maximum latency of the cache during the specified reporting interval.
Cache Misses
The number of failed key lookups during the specified reporting interval. This number maps to keyspace_misses from the Redis INFO command. Cache misses don't necessarily mean there's an issue with the cache. For example, when using the cache-aside programming pattern, an application looks first in the cache for an item. If the item isn't there (cache miss), the item is retrieved from the database and added to the cache for next time. Cache misses are normal behavior for the cache-aside programming pattern. If the number of cache misses is higher than expected, examine the application logic that populates and reads from the cache. If items are being evicted from the cache because of memory pressure, then there may be some cache misses, but a better metric to monitor for memory pressure would be Used Memory or Evicted Keys.
Cache Miss Rate
The percent of unsuccessful key lookups during the specified reporting interval. This metric isn't available in Enterprise or Enterprise Flash tier caches.
Cache Read
The amount of data read from the cache in Megabytes per second (MB/s) during the specified reporting interval. This value is derived from the network interface cards that support the virtual machine that hosts the cache and isn't Redis specific. This value corresponds to the network bandwidth used by this cache. If you want to set up alerts for server-side network bandwidth limits, then create it using this Cache Read counter. See this table for the observed bandwidth limits for various cache pricing tiers and sizes.
Cache Write
The amount of data written to the cache in Megabytes per second (MB/s) during the specified reporting interval. This value is derived from the network interface cards that support the virtual machine that hosts the cache and isn't Redis specific. This value corresponds to the network bandwidth of data sent to the cache from the client.
Connected Clients
The number of client connections to the cache during the specified reporting interval. This number maps to connected_clients from the Redis INFO command. Once the connection limit is reached, later attempts to connect to the cache fail. Even if there are no active client applications, there may still be a few instances of connected clients because of internal processes and connections.
Connections Created Per Second
The number of instantaneous connections created per second on the cache via port 6379 or 6380 (SSL). This metric can help identify whether clients are frequently disconnecting and reconnecting, which can cause higher CPU usage and Redis Server Load. This metric isn't available in Enterprise or Enterprise Flash tier caches.
Connections Closed Per Second
The number of instantaneous connections closed per second on the cache via port 6379 or 6380 (SSL). This metric can help identify whether clients are frequently disconnecting and reconnecting, which can cause higher CPU usage and Redis Server Load. This metric isn't available in Enterprise or Enterprise Flash tier caches.
CPU
The CPU utilization of the Azure Cache for Redis server as a percentage during the specified reporting interval. This value maps to the operating system \Processor(_Total)\% Processor Time performance counter. Note: This metric can be noisy due to low priority background security processes running on the node, so we recommend monitoring Server Load metric to track load on a Redis server.
Errors
Specific failures and performance issues that the cache could be experiencing during a specified reporting interval. This metric has eight dimensions representing different error types, but could have more added in the future. The error types represented now are as follows:
Failover – when a cache fails over (subordinate promotes to primary)
Dataloss – when there's data loss on the cache
UnresponsiveClients – when the clients aren't reading data from the server fast enough, and specifically, when the number of bytes in the Redis server output buffer for a client goes over 1,000,000 bytes
AOF – when there's an issue related to AOF persistence
RDB – when there's an issue related to RDB persistence
Import – when there's an issue related to Import RDB
Export – when there's an issue related to Export RDB
Evicted Keys
The number of items evicted from the cache during the specified reporting interval because of the maxmemory limit.
This number maps to evicted_keys from the Redis INFO command.
Expired Keys
The number of items expired from the cache during the specified reporting interval. This value maps to expired_keys from the Redis INFO command.
