# Домашнее задание к занятию "3.8. Компьютерные сети, лекция 3"

## 1. Подключитесь к публичному маршрутизатору в интернет. Найдите маршрут к вашему публичному IP
```
route-views>show ip route 46.191.249.169
Routing entry for 46.191.248.0/22
  Known via "bgp 6447", distance 20, metric 0
  Tag 3303, type external
  Last update from 217.192.89.50 5d13h ago
  Routing Descriptor Blocks:
  * 217.192.89.50, from 217.192.89.50, 5d13h ago
      Route metric is 0, traffic share count is 1
      AS Hops 3
      Route tag 3303
      MPLS label: none
```

```
route-views>show bgp 46.191.249.169
BGP routing table entry for 46.191.248.0/22, version 2281943578
Paths: (24 available, best #16, table default)
  Not advertised to any peer
  Refresh Epoch 1
  7018 1299 31133 41704
    12.0.1.63 from 12.0.1.63 (12.0.1.63)
      Origin IGP, localpref 100, valid, external
      Community: 7018:5000 7018:37232
      path 7FE022CAF560 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  4901 6079 1299 31133 41704
    162.250.137.254 from 162.250.137.254 (162.250.137.254)
      Origin IGP, localpref 100, valid, external
      Community: 65000:10100 65000:10300 65000:10400
      path 7FE038CF00E8 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  53767 174 31133 41704
    162.251.163.2 from 162.251.163.2 (162.251.162.3)
      Origin IGP, localpref 100, valid, external
      Community: 174:21101 174:22014 53767:5000
      path 7FE0F98BC1D0 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  6939 31133 41704
    64.71.137.241 from 64.71.137.241 (216.218.252.164)
      Origin IGP, localpref 100, valid, external
      path 7FE0050A6900 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  20912 3257 174 31133 41704
    212.66.96.126 from 212.66.96.126 (212.66.96.126)
      Origin IGP, localpref 100, valid, external
      Community: 3257:8070 3257:30155 3257:50001 3257:53900 3257:53902 20912:65004
      path 7FE12AA86AF0 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3561 3910 3356 3216 41704 41704 41704 41704
    206.24.210.80 from 206.24.210.80 (206.24.210.80)
      Origin IGP, localpref 100, valid, external
      path 7FE0E0972F70 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  701 1273 3216 41704 41704 41704 41704
    137.39.3.55 from 137.39.3.55 (137.39.3.55)
      Origin IGP, localpref 100, valid, external
      path 7FE106DE2528 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  8283 31133 41704
    94.142.247.3 from 94.142.247.3 (94.142.247.3)
      Origin IGP, metric 0, localpref 100, valid, external
      Community: 8283:1 8283:101 8283:102
      unknown transitive attribute: flag 0xE0 type 0x20 length 0x24
        value 0000 205B 0000 0000 0000 0001 0000 205B
              0000 0005 0000 0001 0000 205B 0000 0005
              0000 0002
      path 7FE15BD8D738 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3267 31133 41704
    194.85.40.15 from 194.85.40.15 (185.141.126.1)
      Origin IGP, metric 0, localpref 100, valid, external
      path 7FE17EDC7EA8 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3356 3216 41704 41704 41704 41704
    4.68.4.46 from 4.68.4.46 (4.69.184.201)
      Origin IGP, metric 0, localpref 100, valid, external
      Community: 3216:2001 3216:4456 3216:5023 3216:5230 3216:5300 3216:5630 3356:2 3356:22 3356:100 3356:123 3356:503 3356:901 3356:2067
      path 7FE0FF9E7AE0 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3549 3356 3216 41704 41704 41704 41704
    208.51.134.254 from 208.51.134.254 (67.16.168.191)
      Origin IGP, metric 0, localpref 100, valid, external
      Community: 3216:2001 3216:4456 3216:5023 3216:5230 3216:5300 3216:5630 3356:2 3356:22 3356:100 3356:123 3356:503 3356:901 3356:2067 3549:2581 3549:30840
      path 7FE1364B4210 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3333 31133 41704
    193.0.0.56 from 193.0.0.56 (193.0.0.56)
      Origin IGP, localpref 100, valid, external
      path 7FE17B8575F8 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  101 174 31133 41704
    209.124.176.223 from 209.124.176.223 (209.124.176.223)
      Origin IGP, localpref 100, valid, external
      Community: 101:20100 101:20110 101:22100 174:21101 174:22014
      Extended Community: RT:101:22100
      path 7FE01184F898 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  19214 174 31133 41704
    208.74.64.40 from 208.74.64.40 (208.74.64.40)
      Origin IGP, localpref 100, valid, external
      Community: 174:21101 174:22014
      path 7FE16573CAC0 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  20130 6939 31133 41704
    140.192.8.16 from 140.192.8.16 (140.192.8.16)
      Origin IGP, localpref 100, valid, external
      path 7FE049BF5D20 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3303 31133 41704
    217.192.89.50 from 217.192.89.50 (138.187.128.158)
      Origin IGP, localpref 100, valid, external, best
      Community: 3303:1004 3303:1006 3303:1030 3303:3056
      path 7FE0D26D47C8 RPKI State valid
      rx pathid: 0, tx pathid: 0x0
  Refresh Epoch 1
  1351 6939 31133 41704
    132.198.255.253 from 132.198.255.253 (132.198.255.253)
      Origin IGP, localpref 100, valid, external
      path 7FE0DC43DEC8 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  57866 1299 31133 41704
    37.139.139.17 from 37.139.139.17 (37.139.139.17)
      Origin IGP, metric 0, localpref 100, valid, external
      Community: 1299:30000 57866:100 57866:101 57866:501
      path 7FE0A5B2A8F0 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  852 1299 31133 41704
    154.11.12.212 from 154.11.12.212 (96.1.209.43)
      Origin IGP, metric 0, localpref 100, valid, external
      path 7FE116216848 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  7660 2516 1273 3216 41704 41704 41704 41704
    203.181.248.168 from 203.181.248.168 (203.181.248.168)
      Origin IGP, localpref 100, valid, external
      Community: 2516:1030 7660:9001
      path 7FE04D78CEB0 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 2
  2497 174 31133 41704
    202.232.0.2 from 202.232.0.2 (58.138.96.254)
      Origin IGP, localpref 100, valid, external
      path 7FE126826978 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  49788 12552 31133 41704
    91.218.184.60 from 91.218.184.60 (91.218.184.60)
      Origin IGP, localpref 100, valid, external
      Community: 12552:12000 12552:12100 12552:12101 12552:22000
      Extended Community: 0x43:100:1
      path 7FE0CF821018 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  1221 4637 31133 41704
    203.62.252.83 from 203.62.252.83 (203.62.252.83)
      Origin IGP, localpref 100, valid, external
      path 7FE11B5617A8 RPKI State valid
      rx pathid: 0, tx pathid: 0
  Refresh Epoch 1
  3257 1299 31133 41704
    89.149.178.10 from 89.149.178.10 (213.200.83.26)
      Origin IGP, metric 10, localpref 100, valid, external
      Community: 3257:8794 3257:30052 3257:50001 3257:54900 3257:54901
      path 7FE04BE25990 RPKI State valid
      rx pathid: 0, tx pathid: 0
```
      
      
## 2. Создайте dummy0 интерфейс в Ubuntu. Добавьте несколько статических маршрутов. Проверьте таблицу маршрутизации.
Создание интерфейса
```
vim /etc/systemd/network/10-dummy0.netdev
[NetDev]
Name=dummy0
Kind=dummy
EOF
```
```
vim /etc/systemd/network/20-dummy0.network
[Match]
Name=dummy0

[Network]
Address=10.0.8.1/24
EOF
```
Перезагрузка службы
`systemctl restart systemd-networkd`

Проверка
```
root@laptop:~# ifconfig
dummy0: flags=195<UP,BROADCAST,RUNNING,NOARP>  mtu 1500
        inet 10.0.8.1  netmask 255.255.255.0  broadcast 10.0.8.255
        inet6 fe80::58d2:e8ff:fe8d:1471  prefixlen 64  scopeid 0x20<link>
        ether 5a:d2:e8:8d:14:71  txqueuelen 1000  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1  bytes 70 (70.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```
Добавление статического маршрута
```
/etc/netplan/02-networkd.yaml
network:
  version: 2
  ethernets:
    eth0:
      optional: true
      addresses:
        - 10.0.2.3/24
      routes:
        - to: 10.0.4.0/24
          via: 10.0.2.2
```
Проверка создания
```
# ip r
default via 10.0.2.2 dev eth0 proto dhcp src 10.0.2.15 metric 100
10.0.2.0/24 dev eth0 proto kernel scope link src 10.0.2.3
10.0.2.2 dev eth0 proto dhcp scope link src 10.0.2.15 metric 100
10.0.4.0/24 via 10.0.2.2 dev eth0 proto static
10.0.8.0/24 dev dummy0 proto kernel scope link src 10.0.8.1
```

```
# ip r | grep static
10.0.4.0/24 via 10.0.2.2 dev eth0 proto static
```

## 3. Проверьте открытые TCP порты в Ubuntu, какие протоколы и приложения используют эти порты? Приведите несколько примеров.
```
root@laptop:~# ss -tnlp
State   Recv-Q  Send-Q   Local Address:Port      Peer Address:Port  Process
LISTEN  0       64             0.0.0.0:2049           0.0.0.0:*
LISTEN  0       4096           0.0.0.0:42213          0.0.0.0:*      users:(("rpc.mountd",pid=1057,fd=9))
LISTEN  0       4096           0.0.0.0:49673          0.0.0.0:*      users:(("rpc.mountd",pid=1057,fd=17))
LISTEN  0       64             0.0.0.0:37835          0.0.0.0:*
LISTEN  0       4096           0.0.0.0:111            0.0.0.0:*      users:(("rpcbind",pid=866,fd=4),("systemd",pid=1,fd=34))
LISTEN  0       4096     127.0.0.53%lo:53             0.0.0.0:*      users:(("systemd-resolve",pid=868,fd=13))
LISTEN  0       128            0.0.0.0:22             0.0.0.0:*      users:(("sshd",pid=1076,fd=3))
LISTEN  0       4096                 *:9100                 *:*      users:(("node_exporter",pid=1037,fd=3))
```
:53 dns
:22 ssh
:9100 Node_exporter

## 4. Проверьте используемые UDP сокеты в Ubuntu, какие протоколы и приложения используют эти порты?
```
root@laptop:~# ss -unap
State  Recv-Q Send-Q        Local Address:Port    Peer Address:Port Process
UNCONN 0      0                   0.0.0.0:35923        0.0.0.0:*     users:(("avahi-daemon",pid=902,fd=14))
UNCONN 0      0                   0.0.0.0:52925        0.0.0.0:*     users:(("rpc.mountd",pid=1057,fd=16))
UNCONN 0      0             127.0.0.53%lo:53           0.0.0.0:*     users:(("systemd-resolve",pid=868,fd=12))
ESTAB  0      0      192.168.0.102%wlp3s0:68       192.168.0.1:67    users:(("NetworkManager",pid=937,fd=23))
UNCONN 0      0                   0.0.0.0:111          0.0.0.0:*     users:(("rpcbind",pid=866,fd=5),("systemd",pid=1,fd=159))
```
:53 - DNS
:68 - Используется клиентскими машинами для получения информации о динамической IP-адресации от DHCP-сервера.

## 5. Используя diagrams.net, создайте L3 диаграмму вашей домашней сети или любой другой сети, с которой вы работали.
![graph](https://user-images.githubusercontent.com/102476897/168658288-4715faed-a0d9-4387-b717-770300ee76e3.PNG)



