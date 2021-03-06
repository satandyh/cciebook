---
description: 'Лабораторная работа по Теме 1. VLAN, trunking 1.1'
---

# Лабораторная по теме 1

{% file src="../../.gitbook/assets/lab001.zip" caption="Начальная конфигурация" %}

В лабораторной работе может быть несколько заданий соответственно в папках \(task1, task2 и т.д.\). Участникам нужно будет загрузить конечные конфигурации в папки task1, task2 и т.д. в соответствующую папку \(в данной лабораторной работе папка lab001\).

1. 1. Загрузить начальную конфигурацию на SW1, SW2, SW3, SW4 \(внизу страницы\)
   2. На SW1 интерфейсы eth0/1, eth0/2, eth0/3, eth1/0 должны быть в режиме access в таких VLAN, соответственно: 10, 20, 30, 40.
   3. На SW2: интерфейс eth0/2 должен быть в режиме access в VLAN 20. Задать ему имя VLAN: TWENTY.
   4. На SW3: интерфейс eth0/2 добавить в режиме access в VLAN 30. VLAN 30 задать имя THiRTY.
   5. На SW4: интерфейсы eth0/2-3 добавить в режиме access в VLAN 40.
   6. На SW2, порты, подключенные к SW1 перевести в режим режим «desirable» создания транка.
   7. На SW1 порты, подключенные к SW2 перевести в режим ручного создания транка.
   8. На SW3 на портах, подключенных к SW1 создать транк вручную.
   9. Порты между SW4 и SW1 перевести в ручной режим транка и убрать dtp.
   10. На всех транках VLAN 108 должен передаваться нетегированным.
   11. НаSW1 создатьint vlan 20 c ip 10.10.20.10/24, int vlan 30 c ip 10.10.30.10/24, int vlan 40 c ip 10.10.40.10/24
   12. На SW2 создать int vlan 20 с ip 10.10.20.20/24. На SW3 создать int vlan 30 с ip 10.10.30.30/24. На SW4 создать int vlan 40 с ip 10.10.40.40/24
   13. На SW1 разрешить передавать в транках только те VLANы, которые настроены на других коммутаторах.
   14. Отправить пинг с SW1 на 255.255.255.255. Все ip адреса, настроенные на свичах должны пинговаться.

{% file src="../../.gitbook/assets/lab001\_answers.zip" caption="Конечная конфигурация" %}

