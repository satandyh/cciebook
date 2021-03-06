# Задание №1 по теме 64

{% file src="../../../.gitbook/assets/lab064\_task1.zip" caption="Начальная конфигурация" %}

#### Задание №1

1. Для задания используется логическая и физическая топологии проекта.
2. На R2 настроить GRE туннель следующим образом:
   1. В качестве источника туннеля использовать Loopback интерфейс R2
   2. В качестве назначения использовать Loopback интерфейс R9
   3. В качестве IP адреса туннеля использовать Underlay адрес 144.1.0.2/24
   4. Настроить OSPF процесс 100 в Ареа 0 на интерфейсе туннеля и E0/1.12
3. На R9 настроить туннель следующим образом:
   1. В качестве источника туннеля использовать Loopback интерфейс R9
   2. В качестве назначения использовать Loopback интерфейс R2
   3. В качестве IP адреса туннеля использовать Underlay адрес 144.1.0.9/24
   4. Настроить OSPF процесс 100 в Ареа 0 на интерфейсах туннеля и Multilink1
4. Настроить OSPF процесс 100 в Ареа 0 на всех интерфейсах маршрутизаторов R1 и R10 одной командой
5. Настроить фазу 1 IPsec на R2 и R9 следующим образом:
   1. Номер политики 10
   2. Шифрование 3 DES
   3. Хэш MD5
   4. Аутентификация PSK
   5. Diffie-Hellman 5
   6. Для аутентификации пароль брать из названия используемого протокола инкапсуляции VTI, необходимо привязать его к 32-битному адресу пира
6. Настроить фазу 2 IPsec на R2 и R9 следующим образом:
   1. В ACL под названием GRE разрешить все GRE пакеты
   2. Создать Transform Set под названием ESP\_AES\_SHA:
      1. в качестве протокола использовать ESP
      2. в качестве аутентификации использовать HMAC SHA1
   3. Создать Crypto Map под названием GRE\_IPSEC:
      1. будет матчить ACL под названием GRE
      2. будет использовать Transform Set под названием ESP\_AES\_SHA
      3. в качестве пира будет использовать Loopback адреса R2, R9
      4. в качестве локального адреса указать Loopback адреса R2, R9
7. На R2 и R9 применить Crypto Map на следующих интерфесах
   1. R2 — E0/1.23 и E0/1.235
   2. R9 — E0/1.89
8. На интерфейсе Tunnel 0 R2 и R9 изменить значение MTU до 1400 байт и настроить TCP Adjust MSS до 1360

{% file src="../../../.gitbook/assets/lab064\_task1\_answers.zip" caption="Конечная конфигурация" %}

