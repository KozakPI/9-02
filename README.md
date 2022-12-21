Домашнее задание к занятию "9.2. Zabbix. Часть 1" - Козак Павел Иванович

# Задание 1
Установите Zabbix Server с веб-интерфейсом.

Приложите скриншот авторизации в админке. Приложите текст использованных команд в GitHub.

![alt text](https://github.com/KozakPI/png/blob/main/zabbix.png)
![alt text](https://github.com/KozakPI/png/blob/main/zabbix_1.png)

# Последовательность установки

#
wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bdebian11_all.deb

dpkg -i zabbix-release_6.0-4+debian11_all.deb #

apt update
#
apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
#
apt install postgresql
#
 sudo -u postgres createuser --pwprompt zabbix
 sudo -u postgres createdb -O zabbix zabbix
#
zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
#
nano /etc/zabbix/zabbix_server.conf

Редактурую DBPassword=zabbix
#
systemctl restart zabbix-server zabbix-agent apache2  
systemctl enable zabbix-server zabbix-agent apache2
#



# Задание 2

Установите Zabbix Agent на два хоста.

Приложите скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу. Приложите скриншот лога zabbix agent, где видно, что он работает с сервером. Приложите скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные. Приложите текст использованных команд в GitHub.

Я немного промедлил между этими заданями на пару дней, ещё с гитом учился работать и кажется ещё не научился, короче по DHCP zab_ser уже получил другой IP, чем был скрин от задания №1 , но подключил два хоста к серверу скрин прилагаю, в zabbix_agentd.conf адрес сервера указал.
![alt text](https://github.com/KozakPI/png/blob/main/zabbix2_1.png)

На двух хостах прописал 
#
wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bdebian11_all.deb

dpkg -i zabbix-release_6.0-4+debian11_all.deb

apt update
#
apt install zabbix-agent
#
systemctl restart zabbix-agent 

systemctl enable zabbix-agent
#


# Задание 3*
Установите Zabbix Agent на Windows компьютер и подключите его к серверу Zabbix.

Приложите скриншот раздела Latest Data, где видно свободное место на диске C:
