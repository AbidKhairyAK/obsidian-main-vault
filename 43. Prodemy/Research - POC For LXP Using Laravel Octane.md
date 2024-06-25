---
theme: gaia
_class: lead
paginate: true
backgroundColor: "#fff"
backgroundImage: url('https://marp.app/assets/hero-background.svg')
---

# **PoC for LXP**

**- Laravel Octane Performance Benchmarking -**

---
## What Is Laravel Octane

[Laravel Octane](https://github.com/laravel/octane) supercharges PHP application's performance by serving it using high-powered application servers, including [FrankenPHP](https://frankenphp.dev/), [Open Swoole](https://openswoole.com/), [Swoole](https://github.com/swoole/swoole-src), and [RoadRunner](https://roadrunner.dev). 

Octane boots PHP application once, keeps it in memory, and then feeds it requests at supersonic speeds.

---
## Target Web

We will use a simple online course website built using Laravel for this comparison. the DB uses sqlite. there is 2 page on this site that will be:

- Blank page, no db call
  http://nat3.reconv.pl:5825/home
  
- Course Detail, single course detail from db with embedded video from youtube
  http://nat3.reconv.pl:5825/courses/1

---
## Host Server Specs

- NAT server with 10 open port
- 4 cpu 2800Mhz,  0% - 2% on idle
- 4gb RAM, 200mb on idle
- 54gb SSD

---
## Stack Combinations To Compare

- Laravel + Nginx + PHP-FPM
- Laravel + FrankenPHP
- Laravel + RoadRunner

---
## Bencmarking Tools

[wrk](https://github.com/wg/wrk) is a modern HTTP benchmarking tool capable of generating significant load when run on a single multi-core CPU.

Options:
```
-c, --connections: total number of HTTP connections to keep open with
                   each thread handling N = connections/threads

-d, --duration:    duration of the test, e.g. 2s, 2m, 2h

-t, --threads:     total number of threads to use```

    --latency:     print detailed latency statistics
```

---
## Benchmarking Comparison Parameters

- Total Request
- Requests Per Seconds
- Average Latency
- Timed out Requests
- Host CPU Single Core Avg Usage % 
- Host RAM Avg Usage %

---
## Benchmarking Method

- wrk command will be executed from another server
- we will test each 3 stacks, which each of it contains 2 pages
- there is 2 types of test of each pages: 
	- wrk 1 thread & 12 concurrent connections
	- wrk 4 thread & 32 concurrent connections => host server throttle
- duration of each test is 30 seconds
- every test will be executed 2 times, first run is dry run / warm up, and the second run is used as final result

---
<!-- _class: lead -->
# **Benchmark Result**

---
## Blank Page - 12 Connection

| Stack      | Total Reqs | Reqs/Sec | Avg Latency | Timeout | CPU % | RAM % |
| ---------- | ---------- | -------- | ----------- | ------- | ----- | ----- |
| PHP-FPM    |            |          |             |         |       |       |
| FrankenPHP |            |          |             |         |       |       |
| RoadRunner |            |          |             |         |       |       |

---
## Blank Page - 32 Connection

| Stack      | Total Reqs | Reqs/Sec | Avg Latency | Timeout | CPU % | RAM % |
| ---------- | ---------- | -------- | ----------- | ------- | ----- | ----- |
| PHP-FPM    |            |          |             |         |       |       |
| FrankenPHP |            |          |             |         |       |       |
| RoadRunner |            |          |             |         |       |       |

---
## Course Detail Page - 12 Connection

| Stack      | Total Reqs | Reqs/Sec | Avg Latency | Timeout | CPU % | RAM % |
| ---------- | ---------- | -------- | ----------- | ------- | ----- | ----- |
| PHP-FPM    |            |          |             |         |       |       |
| FrankenPHP |            |          |             |         |       |       |
| RoadRunner |            |          |             |         |       |       |

---
## Course Detail Page - 32 Connection

| Stack      | Total Reqs | Reqs/Sec | Avg Latency | Timeout | CPU % | RAM % |
| ---------- | ---------- | -------- | ----------- | ------- | ----- | ----- |
| PHP-FPM    |            |          |             |         |       |       |
| FrankenPHP |            |          |             |         |       |       |
| RoadRunner |            |          |             |         |       |       |

---
## Conclusion


idle: 200
used: 432