# "3.6. Компьютерные сети, лекция 1"
## 1. Работа c HTTP через телнет.
Подключитесь утилитой телнет к сайту stackoverflow.com telnet stackoverflow.com 80
отправьте HTTP запрос
```
GET /questions HTTP/1.0
HOST: stackoverflow.com
[press enter]
[press enter]
```
> В ответе укажите полученный HTTP код, что он означает?
```
$ telnet stackoverflow.com 80
Trying 151.101.1.69...
Connected to stackoverflow.com.
```

```
valera@laptop:~$ telnet stackoverflow.com 80
Trying 151.101.193.69...
Connected to stackoverflow.com.
Escape character is '^]'.
GET /questions HTTP/1.0
HOST: stackoverflow.com

HTTP/1.1 301 Moved Permanently
cache-control: no-cache, no-store, must-revalidate
location: https://stackoverflow.com/questions
x-request-guid: 81a762c5-f475-40a6-9358-d445b8f15080
feature-policy: microphone 'none'; speaker 'none'
content-security-policy: upgrade-insecure-requests; frame-ancestors 'self' https://stackexchange.com
Accept-Ranges: bytes
Date: Tue, 03 May 2022 08:54:12 GMT
Via: 1.1 varnish
Connection: close
X-Served-By: cache-bma1668-BMA
X-Cache: MISS
X-Cache-Hits: 0
X-Timer: S1651568052.914579,VS0,VE101
Vary: Fastly-SSL
X-DNS-Prefetch-Control: off
Set-Cookie: prov=d3917495-71ca-5fbe-9327-c2624fc2931f; domain=.stackoverflow.com; expires=Fri, 01-Jan-2055 00:00:00 GMT; path=/; HttpOnly

```
В ответ получили код 301 - редирект с HTTP на HTTPS протокол того же url

## 2. Повторите задание 1 в браузере, используя консоль разработчика F12.

![console](https://user-images.githubusercontent.com/102476897/166429688-88f344d5-c164-4b0e-9425-79fc9fa381cc.PNG)

1. Получили 200 Internal redirect
2. Страница полностью загрузилась за 996 ms 
3. Самый долгий запрос - начальная загрузка страницы 390ms, потом совокупная загрузка контента.

## 3. Какой IP адрес у вас в интернете?
```
~$ dig @resolver4.opendns.com myip.opendns.com +short
46.191.249.169
```

## 4. Какому провайдеру принадлежит ваш IP адрес? Какой автономной системе AS? Воспользуйтесь утилитой whois
```
valera@laptop:~$ whois 46.191.249.169 | grep descr
descr:          JSC "Ufanet"
descr:          Ufa, Russia
descr:          JSC "Ufanet", Ufa, Russia
```
```
$ whois 46.191.249.169 | grep origin
origin:         AS41704
```
## 5. Через какие сети проходит пакет, отправленный с вашего компьютера на адрес 8.8.8.8? Через какие AS?
```
$ traceroute -An 8.8.8.8
traceroute to 8.8.8.8 (8.8.8.8), 30 hops max, 60 byte packets
 1  192.168.0.1 [*]  2.220 ms  2.329 ms  3.464 ms
 2  145.255.20.253 [AS41704]  5.485 ms  5.445 ms  5.924 ms
 3  145.255.20.241 [AS41704]  6.293 ms  6.722 ms  6.672 ms
 4  79.140.16.177 [AS41704]  8.831 ms 79.140.16.209 [AS41704]  8.796 ms 79.140.16.193 [AS41704]  8.740 ms
 5  10.2.168.1 [*]  8.710 ms  8.696 ms  8.670 ms
 6  10.1.245.17 [*]  8.493 ms  1.790 ms  1.466 ms
 7  10.1.245.130 [*]  6.046 ms  5.983 ms  5.937 ms
 8  212.46.219.109 [AS3216]  5.720 ms  5.987 ms  6.331 ms
 9  79.104.235.215 [AS3216]  29.366 ms 79.104.235.213 [AS3216]  28.264 ms 79.104.225.13 [AS3216]  36.834 ms
10  72.14.213.116 [AS15169]  28.062 ms 72.14.205.76 [AS15169]  32.630 ms  33.831 ms
11  108.170.250.113 [AS15169]  49.334 ms 108.170.250.66 [AS15169]  49.343 ms 108.170.250.99 [AS15169]  49.130 ms
12  216.239.51.32 [AS15169]  52.532 ms 142.251.238.82 [AS15169]  51.966 ms 209.85.255.136 [AS15169]  49.501 ms
13  108.170.232.251 [AS15169]  53.101 ms 172.253.66.110 [AS15169]  51.531 ms 66.249.95.224 [AS15169]  58.600 ms
14  216.239.63.27 [AS15169]  64.470 ms 172.253.64.53 [AS15169]  64.397 ms 209.85.246.111 [AS15169]  64.233 ms
15  * * *
16  * * *
17  * * *
18  * * *
19  * * *
20  * * *
21  * * *
22  * * *
23  * * *
24  8.8.8.8 [AS15169]  53.408 ms  54.314 ms  54.291 ms
```
> AS: [AS41704][AS3216][AS15169]
```
$ grep org-name <(whois AS41704)
org-name:       JSC "Ufanet"
$ grep org-name <(whois AS3216)
org-name:       PJSC "Vimpelcom"
$whois AS15169
OrgTechName:   Google LLC
```
## 6. Повторите задание 5 в утилите mtr. На каком участке наибольшая задержка - delay?
```
$ mtr 8.8.8.8 -znrc 1
Start: 2022-05-03T14:32:22+0500
HOST: laptop                      Loss%   Snt   Last   Avg  Best  Wrst StDev
  1. AS???    192.168.0.1          0.0%     1    1.6   1.6   1.6   1.6   0.0
  2. AS41704  145.255.20.253       0.0%     1    1.8   1.8   1.8   1.8   0.0
  3. AS41704  145.255.20.241       0.0%     1    2.9   2.9   2.9   2.9   0.0
  4. AS41704  79.140.16.209        0.0%     1    2.7   2.7   2.7   2.7   0.0
  5. AS???    10.2.168.1           0.0%     1    3.8   3.8   3.8   3.8   0.0
  6. AS???    10.1.245.17          0.0%     1    3.3   3.3   3.3   3.3   0.0
  7. AS???    10.1.245.130         0.0%     1    4.6   4.6   4.6   4.6   0.0
  8. AS???    10.1.190.70          0.0%     1    2.6   2.6   2.6   2.6   0.0
  9. AS3216   212.46.219.109       0.0%     1   14.0  14.0  14.0  14.0   0.0
 10. AS???    79.104.225.15        0.0%     1   32.8  32.8  32.8  32.8   0.0
 11. AS3216   81.211.29.103        0.0%     1   30.0  30.0  30.0  30.0   0.0
 12. AS???    ???                 100.0     1    0.0   0.0   0.0   0.0   0.0
 13. AS15169  216.239.51.32        0.0%     1   51.4  51.4  51.4  51.4   0.0
 14. AS15169  74.125.253.109       0.0%     1   50.6  50.6  50.6  50.6   0.0
 15. AS15169  142.250.56.127       0.0%     1   50.4  50.4  50.4  50.4   0.0
 16. AS???    ???                 100.0     1    0.0   0.0   0.0   0.0   0.0
 17. AS???    ???                 100.0     1    0.0   0.0   0.0   0.0   0.0
 18. AS???    ???                 100.0     1    0.0   0.0   0.0   0.0   0.0
 19. AS???    ???                 100.0     1    0.0   0.0   0.0   0.0   0.0
 20. AS???    ???                 100.0     1    0.0   0.0   0.0   0.0   0.0
 21. AS???    ???                 100.0     1    0.0   0.0   0.0   0.0   0.0
 22. AS???    ???                 100.0     1    0.0   0.0   0.0   0.0   0.0
 23. AS???    ???                 100.0     1    0.0   0.0   0.0   0.0   0.0
 24. AS???    ???                 100.0     1    0.0   0.0   0.0   0.0   0.0
 25. AS15169  8.8.8.8              0.0%     1   50.4  50.4  50.4  50.4   0.0
```
> 13 хоп с наибольшим делеем.

## 7. Какие DNS сервера отвечают за доменное имя dns.google? Какие A записи? воспользуйтесь утилитой dig
```
$ dig +short NS dns.google
ns3.zdns.google.
ns2.zdns.google.
ns4.zdns.google.
ns1.zdns.google.
```
```
$ dig +short A dns.google
8.8.8.8
8.8.4.4
```
## 8. Проверьте PTR записи для IP адресов из задания 7. Какое доменное имя привязано к IP? воспользуйтесь утилитой dig
```
$ for ip in `dig +short A dns.google`; do dig -x $ip | grep ^[0-9].*in-addr; done
4.4.8.8.in-addr.arpa.	18695	IN	PTR	dns.google.
8.8.8.8.in-addr.arpa.	19012	IN	PTR	dns.google.
```







