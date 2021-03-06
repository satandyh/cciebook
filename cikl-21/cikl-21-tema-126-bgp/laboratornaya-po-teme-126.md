---
description: 'Цикл 21, Тема 126: BGP'
---

# Лабораторная по теме 126

1. В качестве начальной конфигурации использовать конечную конфигурацию лабораторного задания 122.
2. Для задания используется логическая и физическая топологии проекта.
3. R3 и R5 выступают в качестве Транзитных маршрутизаторов, трафик которых может проходить через AS 764 от одного транзитного маршрутизатора к другрму, но внутренние префиксы AS 764 не передаются ни одному Транзитному маршрутизатору.
4. R2 и R8 выступают в качестве Клиентских маршрутизаторов, которые могут достигать внутренних префиксов AS 764, также могут проходить через AS 764 и достигать префиксов Транзитных маршрутизаторов. Также префиксы Клиентских маршрутизаторов могут передаваться Транзитным маршрутизаторам. Но трафик от одного Клиентского маршрутизатора не может передаваться к другому.
5. Настроить R4, R6 и R7 в качестве маршрутизаторов ISP следующим образом:
   1. Настроить команду при которой десятичный формат Community преобразуется в вид AA:NN, где AA — это номер автономной системы, а NN — это произвозльное число
   2. На маршрутизаторе R7:
      1. Настроить Route Map под названием customer-21:
         1. проставить community 21:3
      2. Настроить Route Map под названием customer-108:
         1. проставить community 108:3
      3. Применить Route Map под названием customer-21 по отношению к R2 на входе
      4. Применить Route Map под названием customer-108 по отношению к R8 на входе
      5. Применить в настройках протокола BGP комманду send-community по отношению к R2 и R8
      6. Настроить AS -path ACL под номером 10, где разрешить все маршруты с пустым списком AS\_PATH
      7. Настроить Expanded Community List под названием Permit\_transit, где разрешить любой префикс, который адвертайзится от Транзитных маршрутизаторов.
      8. Настроить Route Map под названием Customers:
         1. Разрешить и заматчить AS -path ACL под номером 10
         2. Разрешить и заматчить Expanded Community List под названием Permit\_transit
         3. Запретить все остальные маршруты
      9. Применить под названием Customers по отношению к R2 и R8 на выходе
   3. На маршрутизаторе R4:
      1. Настроить Route Map под названием transit-3:
         1. проставить community 3:1
      2. Применить Route Map под под названием transit-3 по отношению к R3 на входе
      3. Применить в настройках протокола BGP комманду send-community по отношению к R3
      4. Настроить Community List под номером 200 для идентифицирования префиксов, принадлежащих Клиентским маршрутизаторам AA:3 и Транзитным маршрутизаторам АА:1.
      5. Настроить Route Map под названием Transit\_Partners:
         1. Разрешить и заматчить Community List под номером 200
         2. Запретить все остальные маршруты
      6. Применить Route Map под под названиемTransit\_Partners по отношению к R3 на выходе
   4. На маршрутизаторе R6:
      1. Настроить Route Map под названием transit-5:
         1. проставить community 3:1
      2. Применить Route Map под под названием transit-5 по отношению к R5 на входе
      3. Применить в настройках протокола BGP комманду send-community по отношению к R5
      4. Настроить Community List под номером 200 для идентифицирования префиксов, принадлежащих Клиентским маршрутизаторам AA:3 и Транзитным маршрутизаторам АА:1.
      5. Настроить Route Map под названием Transit\_Partners:
         1. Разрешить и заматчить Community List под номером 200
         2. Запретить все остальные маршруты
      6. Применить Route Map под под названиемTransit\_Partners по отношению к R5 на выходе
6. На маршрутизаторе R2 редистрибьютить все Connected маршруты в BGP процессе 21.
7. На маршрутизаторе R3 редистрибьютить все Connected маршруты в BGP процессе 3.
8. На маршрутизаторе R5 редистрибьютить все Connected маршруты в BGP процессе 5.
9. Проверить выполнение условий задания

