# :white_check_mark: NETWHAT

- [What is an IP address](#p1)
- [What is a Netmask](#p2)
- [What is the subnet of an IP with Netmask](#p3)
- [What is the broadcast address of a subnet](#p4)
- [What are the different ways to represent an ip address with the Netmask](#p5)
- [What are the differences between public and private IPs](#p6)
- [What is a class of IP addresses](#p7)
- [What is TCP](#p8)
- [What is UDP](#p9)
- [What are the network layers](#p10)
- [What is the OSI model](#p11)
- [What is a DHCP server and the DHCP protocol](#p12)
- [What is a DNS server and the DNS protocol](#p13)
- [What are the rules to make 2 devices communicate using IP addresses](#p14)
- [How does routing work with IP](#p15)
- [What is a default gateway for routing](#p16)
- [What is a port from an IP point of view and what is it used for when connecting to another device](#p17)

## What is an IP addres <a name="p1"></a>

Internet Protocol Address («адрес Интернет-протокола») — адрес компьютера, сервера или любой другой активной сетевой железки. Чтобы общаться с другими компьютерами и серверами нужно чтобы у него был уникальный идентификатор, чтобы понять, куда нужно слать данные, и как их получить обратно.
Бывает IPv4 (имеет длину 4 байта) и IPv6 (имеет длину 16 байт).
В 4-й версии IP-адрес представляет собой 32-битное число. Как правило, адрес записывается в виде четырёх десятичных чисел значением от 0 до 255, разделённых точками, например, 192.168.0.3.
В 6-й версии IP-адрес является 128-битным. Как правило, адрес записывается в виде восьми четырёхзначных шестнадцатеричных чисел , разделённых двоеточиями, например, 2001:0db8:85a3:0000:0000:8a2e:0370:7334.

## What is a Netmask <a name="p2"></a>

Маска подсети. Состоит из 32 бит, среди которых слева находится некоторое количество единиц, а остальные биты равны нулю (сначала N единиц, потом 32-N - нулей). Маска подсети - битовая маска, определяющая, какая часть IP - адреса узла сети относится к адресу сети, а какая к адресу самого узла этой сети.

## What is the subnet of an IP with Netmask <a name="p3"></a>

Чтобы определить границы подсети, компьютер делает побитовое умножение (логическое И) между IP-адресом и маской, получая на выходе адрес с обнуленными битами в позициях нулей маски.

Пример:

192.168.11.10 /21

IP-address: 11000000.10101000.00001011.00001010
Netmask: 11111111.11111111.11111000.00000000

![](https://github.com/ntomika/netwhat/raw/main/img/subnetIP.png) 

11000000.10101000.00001000.00000000 = 192.168.8.0 - адрес подсети со всеми обнулёнными битами на позициях, соответствующим нулям в маске.
Если эти биты установить в единицы, то получится широковещательный адрес 192.168.15.255.
Все адреса в диапазоне 192.168.8.1 - 192.168.15.254 являются адресами хостов внутри подсети 192.168.8.0/21 ( 192.168.8.0 и 192.168.15.255 использовать нельзя).

Количество хостов в подсети определяется как 2^(32-N) - 2, где N — длина маски. Чем длиннее маска, тем меньше в ней хостов.

## What are the different ways to represent an ip address with the Netmask <a name="p5"></a>

 192.168.11.10 /21 или 192.168.11.10 с маской 255.255.248.0

## What are the differences between public and private IPs <a name="p6"></a>

IP бывают белые и серые (или публичные и частные). Публичным IP адресом называется IP адрес, который используется для выхода в Интернет. Адреса, используемые в локальных сетях, относят к частным. Частные IP не маршрутизируются в Интернете.
Частные IP-адреса

10.0.0.0 — 10.255.255.255 (маска /8)

172.16.0.0 — 172.31.255.255 (маска /12)

192.168.0.0 — 192.168.255.255 (маска /16)

100.64.0.0 — 100.127.255.255 (маска /10)

## What is a class of IP addresses <a name="p7"></a>

![](https://github.com/ntomika/netwhat/raw/main/img/private.png) 
