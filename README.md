Домашнее задание к занятию "9.2. Zabbix. Часть 1" - Козак Павел Иванович

Задание 1
Установите Zabbix Server с веб-интерфейсом.

Приложите скриншот авторизации в админке. Приложите текст использованных команд в GitHub.

![alt text](https://github.com/KozakPI/png/blob/main/zabbix.png)
![alt text](https://github.com/KozakPI/png/blob/main/zabbix_1.png)
Последовательность установки
1)
# wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bdebian11_all.deb
# dpkg -i zabbix-release_6.0-4+debian11_all.deb
# apt update
2)
# apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
3)
# apt install postgresql
4)
# sudo -u postgres createuser --pwprompt zabbix
# sudo -u postgres createdb -O zabbix zabbix

Задание 2
Установите Zabbix Agent на два хоста.

Приложите скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу. Приложите скриншот лога zabbix agent, где видно, что он работает с сервером. Приложите скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные. Приложите текст использованных команд в GitHub.

Дополнительное задание (со звездочкой*)
Это задание дополнительное (необязательное к выполнению) и никак не повлияют на получение вами зачета по этому домашнему заданию. Вы можете его выполнить, если хотите глубже и/или шире разобраться в материале.

Задание 3*
Установите Zabbix Agent на Windows компьютер и подключите его к серверу Zabbix.

Приложите скриншот раздела Latest Data, где видно свободное место на диске C:
