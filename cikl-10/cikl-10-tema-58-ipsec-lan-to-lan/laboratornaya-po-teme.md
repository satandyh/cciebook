---
description: 'Цикл 10, Тема 58: IPsec LAN-to-LAN'
---

# Лабораторная по теме 58

{% file src="../../.gitbook/assets/lab058.zip" caption="Начальная конфигурация" %}

1. Для задания используется логическая и физическая топологии проекта.
2. На маршрутизаторах R9 и R2 настроить политику ISAKMP следующим образом:
   1. Номер политики 10
   2. Настроить аутентификацию PSK c паролем IPsec, в качестве адресов указать IP адреса Loopback интерфейсов.
   3. Настроить шифрование AES с длиной ключа, равной первым 8 битам IP адресов класса «С» в десятичной системе измерения.
   4. Настроить DH под номером 5
   5. Настроить hash — SHA 384
3. На маршрутизаторах R9 и R2 настроить Crypto Map следующим образом:
   1. Название Cryp\_Map с порядковым номером 10 и политикой ISAKMP
   2. В качестве пира указать ip адреса Loopback интерфейсов.
   3. в качестве источника указать ip адреса Loopback интерфейсов.
4. Настроить расширенный ACL следующим образом:
   1. Название R1\_R10
   2. Разрешить трафик идущий от R1 к R10 и обратно
5. Применить ACL к Crypto Map
6. Настроить Transform Set следующим образом:
   1. Название — ESP\_AES\_192\_SHA1
   2. Настроить политику согласно названию
   3. режим — оставить по-умолчанию
7. Применить Transform Set к Crypto Map
8. Применить Crypto Map к исходящим интерфейсам от R2 к R9 и в обратную сторону.
9. Проверить работу туннеля

{% file src="../../.gitbook/assets/lab058\_answers.zip" caption="Конечная конфигурация" %}

