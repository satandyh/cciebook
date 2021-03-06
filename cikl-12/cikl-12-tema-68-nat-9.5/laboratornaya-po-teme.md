---
description: 'Цикл 12, Тема 68: NAT 9.5'
---

# Лабораторная по теме 68

{% file src="../../.gitbook/assets/lab068.zip" caption="Начальная конфигурация" %}

1. Загрузить начальную конфигурацию всех устройств.
2. Для задания используется логическая и физическая топологии проекта.
3. Для связности в начальной конфигурации настроен протокол OSPF.
4. На R3 настроить GRE туннель следующим образом:
   1. В качестве источника туннеля использовать Loopback интерфейс R3
   2. В качестве назначения использовать Loopback интерфейс R7
   3. В качестве IP адреса туннеля использовать Underlay адрес 144.1.0.3/24
   4. Настроить OSPF процесс 100 в Ареа 144 на интерфейсе туннеля
5. На R7 настроить туннель следующим образом:
   1. В качестве источника туннеля использовать Loopback интерфейс R7
   2. В качестве назначения использовать Loopback интерфейс R3
   3. В качестве IP адреса туннеля использовать Underlay адрес 144.1.0.7/24
   4. Настроить OSPF процесс 100 в Ареа 144 на интерфейсе туннеля
6. Настроить Virtual Link на R7 в сторону R6 и обратно
7. Настроить R10 в качестве DNS сервера для всех маршрутизаторов следующим образом:
   1. настроить dns resolving для хоста R10 , используя адреса 180.1.10.10
8. Настроить R7 в качестве DNS сервера для маршрутизаторов, который будет перенаправлять DNS запросы к R10 при обращении к 10.10.10.10
9. Настроить R6 в качестве DNS сервера для маршрутизаторов следующим образом, который будет отвечать на DNS запросы к 180.1.6.6:
   1. настроить dns resolving для хоста R6 , используя адреса 180.1.6.6
10. Настроить на R2 IP SLA под номером 1 следующим образом:
    1. IP SLA должен отправлять DNS запросы на R10
11. Настроить на R7 Static NAT следующим образом:
    1. inside адрес 180.1.10.10 должен транслироваться в outside 10.10.10.10
    2. применить на интерфейсах:
       1. Out- E0/1.67, Tunnel 0
       2. In — E0/1.78
    3. Решить проблему с маршрутизацией транслируемых адресов при помощи статического маршрута.
12. Настроить на R3 NAT c Route Map следующим образом:
    1. Настроить ACL под названием DNS\_R10:
       1. разрешить диапазон адресов 180.1.0.0/16 к хосту 10.10.10.10
       2. разрешить диапазон адресов 188.1.0.0/16 к хосту 10.10.10.10
    2. Настроить ACL под названием DNS\_R6:
       1. разрешить диапазон адресов 180.1.0.0/16 к хосту 180.1.6.6
       2. разрешить диапазон адресов 188.1.0.0/16 к хосту 180.1.6.6
    3. Настроить Route Map под названием DNS\_R10:
       1. при совпадении адреса из ACL DNS\_R10 устанавливать интерфейс Tunnel0
    4. Настроить Route Map под названием DNS\_R6:
       1. при совпадении адреса из ACL DNS\_R6 устанавливать интерфейс E0/1.34
    5. Настроить NAT Inside:
       1. при совпадении Route Map DNS\_R10 использовать интерфейс Tunnel 0
       2. при совпадении Route Map DNS\_R6 использовать интерфейс E0/1.34
    6. применить на интерфейсах:
       1. Out- E0/1.34, E0/1.235, Tunnel 0
       2. In — E0/1.23
13. Настроить IPSec для шифрования всего трафика на R3 и R7 следующим образом:
    1. фазу 1 IPsec
       1. Номер политики 10
       2. Шифрование 3 DES
       3. Хэш MD5
       4. Аутентификация PSK
       5. Diffie-Hellman 5
       6. Источником для пароля «GRE» должен служить Loopback адрес
    2. Настроить фазу 2 IPsec на R3 и R7 следующим образом:
       1. В ACL под названием GRE\_IPSEC разрешить все GRE пакеты
       2. Создать Transform Set под названием ESP\_AES\_SHA:
          1. в качестве протокола использовать ESP
          2. в качестве аутентификации использовать HMAC SHA1
       3. Создать Crypto Map под названием GRE\_IPSEC:
          1. будет матчить ACL под названием GRE\_IPSEC
          2. будет использовать Transform Set под названием ESP\_AES\_SHA
          3. в качестве пира будет использовать Loopback адреса R3, R7
          4. в качестве локального адреса указать Loopback адреса R3, R7
    3. На R3 и R7 применить Crypto Map на следующих интерфейсах:
       1. R3 — E0/1.34, E0/1.235, Tunnel 0
       2. R7 — E0/1.67 и Tunnel 0
14. Проверить работу NAT

{% file src="../../.gitbook/assets/lab068\_answers.zip" caption="Конечная конфигурация" %}

