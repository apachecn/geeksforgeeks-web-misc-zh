# 用 k6

进行性能测试

> 原文:[https://www.geeksforgeeks.org/performance-testing-with-k6/](https://www.geeksforgeeks.org/performance-testing-with-k6/)

**什么是性能和负载测试？**T3】

性能测试是分析产品质量和能力的过程。负载测试是性能测试的一个子集，我们分析应用程序在正常或峰值负载条件下的行为。

**什么是 k6？**T3】

k6 是一个开源的负载测试工具，用于测试 API、微服务和网站的性能。

**先决条件:**安装 [k6](https://k6.io/docs/getting-started/installation) 工具。

**编写您的性能测试脚本:**脚本必须至少包含一个默认函数——这定义了您的 VUs 的入口点，类似于许多其他语言中的 main()函数。默认函数中的代码称为“VU 代码”，只要测试在运行，它就会一遍又一遍地运行。

k6 使用虚拟用户(VUs)的概念，它运行脚本。Duration 是一个字符串，指定测试应该运行的总持续时间。

创建新的负载测试时，您通常要做的第一件事是定义用于测试系统的 HTTP 请求。一个简单的执行 GET 请求的例子如下:

## Javascript

```
import{ sleep } from 'k6';
import http from 'k6/http';

export let options = {
    duration : '1m',
    vus : 50,
};

export default function() {
    http.get('http://test.k6.io/contacts.php');
    sleep(3);
}
```

**您可以使用以下命令在本地运行测试。只需确保先安装** [**k6**](https://k6.io/docs/getting-started/installation) **即可。**

```
$ k6 run performance-test.js

```

**这将产生以下输出:**

```
          /\      |‾‾|  /‾‾/  /‾/
     /\  /  \     |  |_/  /  / /
    /  \/    \    |      |  /  ‾‾\
   /          \   |  |‾\  \ | (_) |
  / __________ \  |__|  \__\ \___/ .io

  execution: local
     script: performance-test.js
     output: -

  scenarios: (100.00%) 1 executors, 50 max VUs, 1m30s max duration (incl. graceful stop):
           * default: 50 looping VUs for 1m0s (gracefulStop: 30s)

running (1m02.5s), 00/50 VUs, 1000 complete and 0 interrupted iterations
default ✓ [======================================] 50 VUs  1m0s

    data_received..............: 711 kB 11 kB/s
    data_sent..................: 88 kB  1.4 kB/s
    http_req_blocked...........: avg=8.97ms   min=1.37µs   med=2.77µs   max=186.58ms p(90)=9.39µs   p(95)=8.85ms
    http_req_connecting........: avg=5.44ms   min=0s       med=0s       max=115.8ms  p(90)=0s       p(95)=5.16ms
    http_req_duration..........: avg=109.39ms min=100.73ms med=108.59ms max=148.3ms  p(90)=114.59ms p(95)=119.62ms
    http_req_receiving.........: avg=55.89µs  min=16.15µs  med=37.92µs  max=9.67ms   p(90)=80.07µs  p(95)=100.34µs
    http_req_sending...........: avg=15.69µs  min=4.94µs   med=10.05µs  max=109.1µs  p(90)=30.32µs  p(95)=45.83µs
    http_req_tls_handshaking...: avg=0s       min=0s       med=0s       max=0s       p(90)=0s       p(95)=0s
    http_req_waiting...........: avg=109.31ms min=100.69ms med=108.49ms max=148.22ms p(90)=114.54ms p(95)=119.56ms
    http_reqs..................: 1000   15.987698/s
    iteration_duration.........: avg=3.11s    min=3.1s     med=3.1s     max=3.3s     p(90)=3.12s    p(95)=3.15s
    iterations.................: 1000   15.987698/s
    vus........................: 50     min=50 max=50
    vus_max....................: 50     min=50 max=50

```

[**HTTP 专用内置 METRIC:**](https://k6.io/docs/using-k6/metrics)

<figure class="table">T18】HTTP _ reqs

| **公制名称** | **描述** |
| How many HTTP requests k6 were generated in total. |
| http _ req _ blocked | Time spent blocking (waiting for idle TCP connection slot) before initiating the request. float |
| http _ req _ connecting | Time spent establishing TCP connection with remote host. float |
| http _ req _ tls _ handling | Time spent shaking TLS session with remote host |
| http _ req _ sending | Time spent sending data to the remote host. float |
| http _ req _ waiting | Time spent waiting for a response from the remote host (also known as "first byte time", or "TTFB"). float |
| http _ req _ 接收 | Time taken to receive response data from the remote host. float |
| http _ req _ duration | 请求的总时间。等于 http _ req _ sending+http _ req _ waiting+http _ req _ receiving . |

</figure>

浮动

**汇总导出:**您也可以通过使用–out/-o 选项将 k6 输出详细的统计数据以 CSV 格式输出，如下所示:

```
$ k6 run --out csv=my_test_result.csv script.js

```