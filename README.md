# `heappy`
## A log analyzer to show heap usage in Hazelcast member logs

(Yes, the name is dumb, but `heap` was already taken on my Mac. )

This is a Python3 log analyzer that uses:

`#!/usr/bin/env python3`

You can take the file named `heappy` and put it somewhere in your path, or run it from wherever you like.

To run it, run `heappy /path/to/your/hazelcast.log`

It prints out information like this:

```
IP: 10.13.255.36
Timestamp: 2023-07-06 05:45:07 INF
Heap Memory Usage: Used=5.8G, Free=2.2G, Total=8.0G, Max=8.0G
Used Heap as Percentage of Total: 72.50%

File: hazelcast.log
IP: 10.13.255.36
Timestamp: 2023-07-06 05:45:27 INF
Heap Memory Usage: Used=6.4G, Free=1.6G, Total=8.0G, Max=8.0G
Used Heap as Percentage of Total: 80.00%

File: hazelcast.log
IP: 10.13.255.36
Timestamp: 2023-07-06 05:48:27 INF
Heap Memory Usage: Used=6.2G, Free=1.8G, Total=8.0G, Max=8.0G
Used Heap as Percentage of Total: 77.50%

File: hazelcast.log
Server IP: 10.13.255.36
Average Used Heap as Percentage of Total: 75.58%
Highest Heap Usage: 86.25% occurred at 2023-07-05 16:48:04 INF
Lowest Heap Usage: 16.25% occurred at 2023-07-04 02:08:01 INF
```

The last group is the summary of the file's data.  If you only want this, run with the `--summary` option.

To quickly understand the heap usage, you can run with `--graph`and you will get an ASCII bar graph like the following.

```
2023-07-04 17:27:59 INF |⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹                              | 71.25%
2023-07-05 05:17:58 INF |⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹                                                          | 43.75%
2023-07-05 06:46:02 INF |⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹                                    | 65.00%
2023-07-05 07:29:02 INF |⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹                                                           | 42.50%
2023-07-05 09:25:02 INF |⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹                                                                              | 23.75%
2023-07-05 11:56:03 INF |⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹⏹                              | 71.25%
