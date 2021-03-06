---
description: 'Цикл 21, Тема 123: IPv4 Multicast Routing'
---

# Лабораторная по теме 123

{% file src="../../.gitbook/assets/lab123.zip" caption="Начальная конфигурация" %}

1. Загрузить начальную конфигурацию всех устройств.
2. Для задания используется логическая и физическая топологии проекта.
3. На маршрутизаторах R1 и R2 настроить OSPF процесс 21 в Аrea 21 на всех интерфейсах:
4. На маршрутизаторах R3, R4, R5, R6 настроить OSPF процесс 6543 в Аrea 6543 на всех интерфейсах:
5. На маршрутизаторах R7, R8, R9, R10 настроить OSPF процесс 10987 в Аrea 10987 на всех интерфейсах.
6. На маршрутизаторах R1, R2 настроить внутренний BGP процесс следующим образом:
   1. Номер AS — 21
   2. Создать bgp сессию следующим образом:
      1. Указать в качестве Remote AS номер 21
      2. Указать в качестве соседей IP адреса интерфейсов Loopback 0
      3. Настроить команду, при которой все Next Hop адреса узнаются через OSPF
      4. На R2 указать R1 в качестве клиента Route Reflector’a
7. На маршрутизаторе R2 настроить внешний BGP процесс следующим образом:
   1. Номер AS — 21
   2. Создать bgp сессию следующим образом:
      1. Указать в качестве Remote AS номер 6543
      2. Указать в качестве соседей IP адреса интерфейсов Loopback 0
      3. Позволить увеличение значения TTL только до 2 хопов
      4. Адвертайзить маршрут 180.1.0.0/22 с помощью команды network
8. На маршрутизаторах R3, R4, R5, R6 настроить Confederation BGP процесс следующим образом:
   1. R3 — номер AS — 3
   2. R4, R5 — номер AS — 54
   3. R6 — номер AS — 6
   4. Создать внешнюю bgp сессию на R3 следующим образом:
      1. Указать в качестве идентификатора конфедерации номер AS 6543
      2. Указать в качестве пиров конфедерации 54
      3. Указать в качестве Remote AS номера AS 21 и 54
      4. Указать в качестве соседей IP адреса интерфейсов Loopback 0
      5. Позволить увеличение значения TTL только до 2 хопов
      6. Для соседа в AS 54 настроить команду, при которой все Next Hop адреса узнаются через OSPF
      7. Адвертайзить маршрут по-умолчанию с помощью команды network
   5. Создать внешнюю и внутреннюю bgp сессии на R4 следующим образом:
      1. Указать в качестве идентификатора конфедерации номер AS 6543
      2. Указать в качестве пиров конфедерации AS номера 3 и 6
      3. Для внешней bgp сессии:
         1. Создать пир группу под названием CONFEDERATION:
            1. Позволить увеличение значения TTL только до 2 хопов
            2. Для соседей настроить команду, при которой все Next Hop адреса узнаются через OSPF
         2. Указать в качестве Remote AS номера AS R3 и R6
         3. Указать в качестве членов группы IP адреса интерфейсов Loopback 0 R3 и R6
      4. Для внутренней bgp сессии:
         1. Создать пир группу под названием REFLECT:
            1. На R4 указать R5 в качестве клиента Route Reflector’a
            2. Для соседа настроить команду, при которой все Next Hop адреса узнаются через OSPF
         2. Указать в качестве Remote AS номер AS 54
         3. Указать в качестве члена группы IP адрес интерфейса Loopback 0 R5
   6. Создать внутреннюю bgp сессию на R5 следующим образом:
      1. Указать в качестве идентификатора конфедерации номер AS 6543
      2. Указать в качестве Remote AS номер AS 54
      3. Для соседа R4 настроить команду, при которой все Next Hop адреса узнаются через OSPF
   7. Создать внешнюю и внутреннюю bgp сессии на R6 следующим образом:
      1. Указать в качестве идентификатора конфедерации номер AS 6543
      2. Указать в качестве пиров конфедерации AS номер 54
      3. Для внешней bgp сессии конфедерации:
         1. Создать пир группу под названием CONFEDERATION:
            1. Позволить увеличение значения TTL только до 2 хопов
            2. Для соседей настроить команду, при которой все Next Hop адреса узнаются через OSPF
         2. Указать в качестве Remote AS номер AS R4
         3. Указать в качестве членов группы IP адрес интерфейса Loopback 0 R4
      4. Для внешней bgp сессии:
         1. Указать в качестве Remote AS номер AS 10987
         2. Указать в качестве члена группы IP адрес интерфейса Loopback 0 R7
         3. Позволить увеличение значения TTL только до 2 хопов
         4. Адвертайзить маршрут по-умолчанию с помощью команды network
9. На маршрутизаторах R7, R8, R8, R10 настроить Confederation BGP процесс следующим образом:
   1. R7 — номер AS — 7
   2. R8, R9, R10 — номер AS — 1098
   3. Создать внешнюю bgp сессию на R7 следующим образом:
      1. Указать в качестве идентификатора конфедерации номер AS 10987
      2. Указать в качестве пиров конфедерации 1098
      3. Указать в качестве Remote AS номера AS 6543 и 1098
      4. Указать в качестве соседей IP адреса интерфейсов Loopback 0
      5. Позволить увеличение значения TTL только до 2 хопов
      6. Для соседа в AS 1098 настроить команду, при которой все Next Hop адреса узнаются через OSPF
      7. Адвертайзить маршрут 180.1.0.0/20 с помощью команды network
   4. Создать внешнюю и внутреннюю bgp сессии на R8 следующим образом:
      1. Указать в качестве идентификатора конфедерации номер AS 10987
      2. Указать в качестве пиров конфедерации AS номер 7
      3. Для внешней bgp сессии:
         1. Создать пир группу под названием CONFEDERATION:
            1. Позволить увеличение значения TTL только до 2 хопов
            2. Для соседа настроить команду, при которой все Next Hop адреса узнаются через OSPF
         2. Указать в качестве Remote AS номер AS R7
         3. Указать в качестве членов группы IP адреса интерфейсов Loopback 0 R7
      4. Для внутренней bgp сессии:
         1. Создать пир группу под названием REFLECT:
            1. Указать R9 в качестве клиента Route Reflector’a
            2. Для соседа настроить команду, при которой все Next Hop адреса узнаются через OSPF
         2. Указать в качестве Remote AS номер AS 1098
         3. Указать в качестве члена группы IP адрес интерфейса Loopback 0 R9
   5. Создать внутреннюю bgp сессию на R9 следующим образом:
      1. Создать пир группу под названием REFLECT:
         1. Для соседа настроить команду, при которой все Next Hop адреса узнаются через OSPF
      2. Указать в качестве Remote AS номер AS 1098
      3. Указать в качестве членов группы IP адреса интерфейсов Loopback 0 R8 и R9
   6. Создать внутреннюю bgp сессию на R10 следующим образом:
      1. Создать пир группу под названием REFLECT:
         1. Для соседа настроить команду, при которой все Next Hop адреса узнаются через OSPF
      2. Указать в качестве Remote AS номер AS 1098
      3. Указать в качестве члена группы IP адрес интерфейса Loopback 0 R9
10. На маршрутизаторах R2 и R3 настроить статические маршруты к друг другу следующим образом:
    1. В качестве маршрута указать IP адрес Loopback0 интерфейса друг друга
    2. В качестве Next Hop указать IP адрес интерфейса E0/1.23 друг друга.
11. На маршрутизаторах R6 и R7 настроить статические маршруты к друг другу следующим образом:
    1. В качестве маршрута указать IP адрес Loopback0 интерфейса друг друга
    2. В качестве Next Hop указать IP адрес интерфейса E0/1.67 друг друга.
12. На маршрутизаторе R3 настроить маршрут по-умолчанию указав в качестве Next Hop интерфейс Null0.
13. На маршрутизаторе R6 настроить маршрут по-умолчанию указав в качестве Next Hop интерфейс Null0.
14. На маршрутизаторе R2 настроить статический маршрут 180.1.0.0/22 указав в качестве Next Hop интерфейс Null0.
15. На маршрутизаторе R7 настроить статический маршрут 180.1.0.0/20 указав в качестве Next Hop интерфейс Null0.
16. На всех маршрутизаторах настроить IP Multicast Routing
17. На всех маршрутизаторах настроить Sparse Mode на следующих интерфейсах:
    1. R1 — E0/1.12, Loopback0
    2. R2 — E0/1.12, E0/1.23, E0/1.235
    3. R3- E0/1.34, E0/1.23, E0/1.235
    4. R4 — E0/1.456, E0/1.23, E0/1.235
    5. R5 — E0/1.456, E0/1.235
    6. R6 -E0/1.67, E0/1.456, Loopback0
    7. R7 — E0/1.78, E0/1.67
    8. R8 — E0/1.78, E0/1.89
    9. R9 — E0/1.89, Multilink 1
    10. R10 — Multilink 1
18. Настроить интерфесы E0/1.67 R6 и R7 в качестве BSR EDGE, роли BSR Candidate и RP, используя при этом Lo интерфейс маршрутизаторов с условием не адвертайзить BSR информацию за пределы настраивомого линка.
19. Настроить интерфейс Multilink1 маршрутизатора R9 качестве клиента группы 224.2.2.2

