#### 🏁 Task:  
Create a cheat sheet or short guide explaining the purpose and usage of each command. Include practical examples like using **ping** to check connectivity or **curl** to request a webpage.

### 4. Hands-On with Networking Commands 🖥️
Knowing networking commands is essential for diagnosing and troubleshooting network issues.

#### Common Networking Commands:
- **ping**: Test the reachability of a host.
  ```text
  ubuntu@ip-172-31-45-204:~$ ping google.com
  PING google.com (74.125.193.102) 56(84) bytes of data.
  64 bytes from di-in-f102.1e100.net (74.125.193.102): icmp_seq=1 ttl=58 time=1.24 ms
  64 bytes from di-in-f102.1e100.net (74.125.193.102): icmp_seq=2 ttl=58 time=0.790 ms
  64 bytes from di-in-f102.1e100.net (74.125.193.102): icmp_seq=3 ttl=58 time=1.33 ms
  --- google.com ping statistics ---
  3 packets transmitted, 3 received, 0% packet loss, time 2011ms
  rtt min/avg/max/mdev = 0.790/1.118/1.327/0.235 ms
  ```
- **traceroute / tracert**: Trace the route packets take to a host.
  ```text
  ubuntu@ip-172-31-45-204:~$ traceroute google.com
  traceroute to google.com (209.85.203.102), 30 hops max, 60 byte packets
  240.4.244.13 (240.4.244.13)  1.713 ms 240.4.244.12 (240.4.244.12)  1.668 ms 240.4.244.13 (240.4.244.13)  1.662 ms
  99.82.10.98 (99.82.10.98)  1.624 ms  1.593 ms  1.567 ms
  99.82.10.99 (99.82.10.99)  1.542 ms  1.516 ms  1.490 ms
  192.178.109.1 (192.178.109.1)  1.709 ms 192.178.107.105 (192.178.107.105)  1.532 ms 192.178.109.35 (192.178.109.35)  1.400 ms
  192.178.107.64 (192.178.107.64)  1.396 ms 192.178.109.20 (192.178.109.20)  1.369 ms 192.178.109.24 (192.178.109.24)  1.514 ms
  74.125.253.185 (74.125.253.185)  1.325 ms 192.178.82.57 (192.178.82.57)  1.746 ms 74.125.253.185 (74.125.253.185)  1.162 ms
  209.85.247.102 (209.85.247.102)  1.559 ms 172.253.71.160 (172.253.71.160)  7.315 ms  7.298 ms
  142.251.70.215 (142.251.70.215)  1.695 ms 142.251.70.163 (142.251.70.163)  1.082 ms 142.251.70.109 (142.251.70.109)  1.827 ms
   * * *
   * * *
   * * *
   * * *
   * * *
   * * *
   * * *
   * * *
   * * *
  dh-in-f102.1e100.net (209.85.203.102)  2.042 ms * *

```
- **netstat**: Display network connections, routing tables, and interface statistics.
```text
ubuntu@ip-172-31-45-204:~$ netstat -tuln
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN
tcp        0      0 127.0.0.1:36911         0.0.0.0:*               LISTEN
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN
tcp        0      0 127.0.0.1:5432          0.0.0.0:*               LISTEN
tcp        0      0 127.0.0.54:53           0.0.0.0:*               LISTEN
tcp6       0      0 :::22                   :::*                    LISTEN
tcp6       0      0 :::80                   :::*                    LISTEN
udp        0      0 127.0.0.1:323           0.0.0.0:*
udp        0      0 127.0.0.54:53           0.0.0.0:*
udp        0      0 127.0.0.53:53           0.0.0.0:*
udp        0      0 172.31.45.204:68        0.0.0.0:*
udp6       0      0 ::1:323                 :::*
```

- **curl**: Transfer data to/from a server, commonly used for making HTTP requests.
  ```text
  curl -vlk https://www.google.com
* Host www.google.com:443 was resolved.
* IPv6: 2a00:1450:400b:c03::6a, 2a00:1450:400b:c03::68, 2a00:1450:400b:c03::67, 2a00:1450:400b:c03::69
* IPv4: 74.125.193.103, 74.125.193.99, 74.125.193.147, 74.125.193.106, 74.125.193.104, 74.125.193.105
*   Trying 74.125.193.103:443...
* Connected to www.google.com (74.125.193.103) port 443
* ALPN: curl offers h2,http/1.1
* TLSv1.3 (OUT), TLS handshake, Client hello (1):
* TLSv1.3 (IN), TLS handshake, Server hello (2):
* TLSv1.3 (IN), TLS handshake, Encrypted Extensions (8):
* TLSv1.3 (IN), TLS handshake, Certificate (11):
* TLSv1.3 (IN), TLS handshake, CERT verify (15):
* TLSv1.3 (IN), TLS handshake, Finished (20):
* TLSv1.3 (OUT), TLS change cipher, Change cipher spec (1):
* TLSv1.3 (OUT), TLS handshake, Finished (20):
* SSL connection using TLSv1.3 / TLS_AES_256_GCM_SHA384 / X25519 / id-ecPublicKey
* ALPN: server accepted h2
* Server certificate:
*  subject: CN=www.google.com
*  start date: Jan 20 08:37:54 2025 GMT
*  expire date: Apr 14 08:37:53 2025 GMT
*  issuer: C=US; O=Google Trust Services; CN=WR2
*  SSL certificate verify result: unable to get local issuer certificate (20), continuing anyway.
*   Certificate level 0: Public key type EC/prime256v1 (256/128 Bits/secBits), signed using sha256WithRSAEncryption
*   Certificate level 1: Public key type RSA (2048/112 Bits/secBits), signed using sha256WithRSAEncryption
*   Certificate level 2: Public key type RSA (4096/152 Bits/secBits), signed using sha256WithRSAEncryption
* using HTTP/2
* [HTTP/2] [1] OPENED stream for https://www.google.com/
* [HTTP/2] [1] [:method: GET]
* [HTTP/2] [1] [:scheme: https]
* [HTTP/2] [1] [:authority: www.google.com]
* [HTTP/2] [1] [:path: /]
* [HTTP/2] [1] [user-agent: curl/8.5.0]
* [HTTP/2] [1] [accept: */*]
> GET / HTTP/2
> Host: www.google.com
> User-Agent: curl/8.5.0
> Accept: */*
>
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* TLSv1.3 (IN), TLS handshake, Newsession Ticket (4):
* old SSL session ID is stale, removing
< HTTP/2 200
< date: Sun, 09 Feb 2025 11:06:20 GMT
< expires: -1
< cache-control: private, max-age=0
< content-type: text/html; charset=ISO-8859-1
< content-security-policy-report-only: object-src 'none';base-uri 'self';script-src 'nonce-1oWFN5xXmVF7_biF_5jV5A' 'strict-dynamic' 'report-sample' 'unsafe-eval' 'unsafe-inline' https: http:;report-uri https://csp.withgoogle.com/csp/gws/other-hp
< accept-ch: Sec-CH-Prefers-Color-Scheme
< p3p: CP="This is not a P3P policy! See g.co/p3phelp for more info."
< server: gws
< x-xss-protection: 0
< x-frame-options: SAMEORIGIN
< set-cookie: AEC=AVcja2cuwYeNi0tvjpJ3QoPVGY5mzuH5dlhVk2A0Ojo2ouSnkHQ2jgRYBuA; expires=Fri, 08-Aug-2025 11:06:20 GMT; path=/; domain=.google.com; Secure; HttpOnly; SameSite=lax
< set-cookie: __Secure-ENID=25.SE=WPPNVwaONjmr3bDTfSyKClPeg_CkxgaxGgLdRZw0CgCSBwbTMHQhaANtHAOgckgAENz02KD-CtCABTeDUMZ1Fz19SFFloQOF5zQIsXrWt7vr2oSzJuZbeICLOO1tZOyPvJWuhOkZoGY3LrWVcj8xkw6g0yPf--l1y4n4RaQBAiUkdk9NFPRF74aPvcx03eCiG3WZT4Ro8QkNRWLjgDpYLZ_VAsKvug7H8NpfR47HuJJznqyIn8byNg; expires=Thu, 12-Mar-2026 03:24:38 GMT; path=/; domain=.google.com; Secure; HttpOnly; SameSite=lax
< alt-svc: h3=":443"; ma=2592000,h3-29=":443"; ma=2592000
< accept-ranges: none
< vary: Accept-Encoding
<
<!doctype html><html itemscope="" itemtype="http://schema.org/WebPage" lang="en-IE"><head><meta content="text/html; charset=UTF-8" http-equiv="Content-Type"><meta content="/images/branding/googleg/1x/googleg_standard_color_128dp.png" itemprop="image"><title>Google</title><script nonce="1oWFN5xXmVF7_biF_5jV5A">(function(){var _g={kEI:'LIyoZ6W3I9nAhbIPhtaD0As',kEXPI:'0,202747,3497545,1092,538661,2872,2891,8348,34680,30022,217969,142932,51394,42849,117808,7734,18673,20675,11343,19568,5240755,768,8835014,84,27977703,25224045,4636,16436,49022,46756,10889,15165,8182,14386,44279,4393,8041,6753,22595,1284,9139,3077,1522,328,6226,2949,25041,6321,16265,13589,1341,5406,8302,15631,12135,5437,239,3494,33,26708,10667,21344,4486,3854,41,13639,1,4922,1614,205,4105,19302,1808,3993,951,2146,4617,5773,4311,2326,1310,738,4381,3586,767,583,6948,2642,20,1745,3,2,2455,514,4905,5943,957,2801,460,41,2,415,2530,15,3442,714,1789,1254,56,1026,1,142,66,330,2,287,1,218,1,703,1057,2554,2244,1038,570,1060,1047,260,423,1,1401,1151,143,465,9,1491,772,375,190,228,296,2,1463,407,354,1029,15,139,3,2759,3,461,720,538,5,101,7,828,6,1553,89,2162,15,360,732,305,3,2,1,2,2,2,3,1443,169,3,58,167,3,126,141,296,28,24,261,290,312,57,159,2,822,889,9,2,346,189,10,633,830,782,227,204,344,35,825,221,1096,97,2,2,122,130,246,155,434,467,717,1,98,326,283,817,1235,683,3,576,18,247,26,259,165,4,98,14,2,3,2,79,2,42,129,85,221,23,7,58,605,875,325,1083,373,422,211,571,41,156,1023,571,355,211,5,723,20955600,375837,4,28852,18,2010,48,2482,8,3873,12,293,650,8023169',kBL:'ASB9',kOPI:89978449};(function(){var a;((a=window.google)==null?0:a.stvsc)?google.kEI=_g.kEI:window.google=_g;}).call(this);})();(function(){google.sn='webhp';google.kHL='en-IE';})();(function(){
```

- **dig / nslookup**: Perform DNS lookups.
```text
ubuntu@ip-172-31-45-204:~$ nslookup google.com
Server:         127.0.0.53
Address:        127.0.0.53#53

Non-authoritative answer:
Name:   google.com
Address: 74.125.193.100
Name:   google.com
Address: 74.125.193.139
Name:   google.com
Address: 74.125.193.113
Name:   google.com
Address: 74.125.193.138
Name:   google.com
Address: 74.125.193.102
Name:   google.com
Address: 74.125.193.101
Name:   google.com
Address: 2a00:1450:400b:c02::66
Name:   google.com
Address: 2a00:1450:400b:c02::64
Name:   google.com
Address: 2a00:1450:400b:c02::8a
Name:   google.com
Address: 2a00:1450:400b:c02::8b
```

