---
description: 'Цикл 9, Тема 53: TCP keepalive, core dumps, debug'
---

# Лабораторная по теме 53

{% file src="../../.gitbook/assets/lab053.zip" caption="Начальная конфигурация" %}

1. Загрузить начальную конфигурацию всех устройств.
2. Для задания используется логическая и физическая топологии проекта.
3. На R2 настроить телнет следующим образом:
   1. создать локального пользователя под именем TelAdmin c привилегией 15 и с шифрованным паролем TeLneT. Включить ААА.
   2. создать authentication list под названием TELNET c использованием локальной базы пользователей. Применить на терминальной линии.
   3. Настроить R2 таким образом, что если он обнаружит неактивную сессию телнет, он сбросит ее.
4. На R9 настроить debug сообщения таким образом, чтобы они показывали сообщения только с интерфеса Multilink1. Приложите вывод команды show debug в решение.

{% file src="../../.gitbook/assets/lab053\_answers.zip" caption="Конечная конфигурация" %}

