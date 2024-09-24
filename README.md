# Django Performance Benchmark Results

## Test Results

| Metric                    | Test 1 (Initial)        | Test 2 (Optimized)      |
|---------------------------|-------------------------|-------------------------|
| **Duration**               | 30s                     | 30s                     |
| **Threads**                | 12                      | 12                      |
| **Connections**            | 400                     | 400                     |
| **Latency (Avg)**          | 43.41ms                 | 43.41ms                 |
| **Latency (Stdev)**        | 8.62ms                  | 8.62ms                  |
| **Latency (Max)**          | 100.58ms                | 100.58ms                |
| **Requests per Second**    | 250.10                  | 250.10                  |
| **Max Requests per Second**| 585.00                  | 585.00                  |
| **Total Requests**         | 16,575                  | 16,575                  |
| **Data Read**              | 4.44MB                  | 4.44MB                  |
| **Socket Errors (Connect)**| 394                     | 394                     |
| **Socket Errors (Read)**   | 3,166                   | 3,166                   |
| **Socket Errors (Write)**  | 166                     | 166                     |
| **Requests/sec**           | 551.18                  | 551.18                  |
| **Transfer/sec**           | 151.25KB                | 151.25KB                |

## Explanation

- **Latency**: Both tests show the same average latency at **43.41ms**, which is responsive, with a low maximum of **100.58ms**.
  
- **Throughput**: Both tests report **250.10 requests per second**, with a maximum of **585 requests per second**. The server processed **16,575 total requests** in each test.

- **Socket errors**: There were a significant number of **connection errors (394)**, **read errors (3,166)**, and **write errors (166)** in both tests. This indicates that there may still be issues with how the server handles concurrency at high loads.

- **Requests/sec & Transfer/sec**: The throughput remained consistent, with **551.18 requests per second** and **151.25KB transfer per second**.

Both tests performed similarly, but the presence of socket errors suggests more optimization is needed, especially for handling concurrent connections efficiently.
