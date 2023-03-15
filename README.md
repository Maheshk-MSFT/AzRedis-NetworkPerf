# AzRedis-NetworkPerf-Metrics-Monitoring-Bandwidth
AzRedis-NetworkPerf-Metrics-Monitoring-Bandwidth

Network Bandwidth
> If the Redis server exceeds the available bandwidth, clients requests could time out because the server can't push data to the client fast enough. Check "Cache Read" > and "Cache Write" metrics to see how much server-side bandwidth is being used. 

> If your Redis server is exceeding available network bandwidth, you should consider scaling up to a larger cache size with higher network bandwidth.

Network monitoring
https://learn.microsoft.com/en-us/azure/azure-cache-for-redis/cache-how-to-scale?WT.mc_id=wwc-aces
https://learn.microsoft.com/en-us/azure/azure-cache-for-redis/cache-how-to-monitor#create-alerts

<img width="640" alt="4" src="https://user-images.githubusercontent.com/61469290/225243289-82166899-1ee0-4ba7-813d-41025df1721d.png">

<img width="663" alt="1" src="https://user-images.githubusercontent.com/61469290/225243190-41732753-f84b-428a-aecd-9c0b7a73f4aa.png">

<img width="784" alt="2" src="https://user-images.githubusercontent.com/61469290/225243221-4c5dd794-42c0-4cc0-bbf3-e8ff9a08a285.png">

<img width="807" alt="3" src="https://user-images.githubusercontent.com/61469290/225243255-f8191704-cc84-49cd-9776-0424f07f1da7.png">

List of metrics
```
Cache Latency (preview)
Cache Misses
Cache Miss Rate
Cache Read - bandwidth 
Cache Write - bandwidth
Connected Clients
Connections Created Per Second
Connections Closed Per Second
CPU
Errors
Evicted Keys
Expired Keys
```
