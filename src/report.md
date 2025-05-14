## Part 1. Installation of the OS
+ ``Ubuntu version``  
![](img/part1/part1.png)
## Part 2. Creating a user
- ``Create a user``  
![](img/part2/part2.png)  
---
- ``Added to adm group``  
![](img/part2/part2-1.png)  
---
- ``cat /etc/passwd``  
![](img/part2/part2-2.png)
## Part 3. Настройка сети ОС
- ``Set the machine name as user-1``  
![](img/part3/Screenshot%202024-07-02%20at%202.04.12%20PM.png)  
---
- ``Set the time zone corresponding to your current location``  
![](img/part3/Screenshot%202024-07-02%20at%202.10.47%20PM.png)  
---
- ``names of the network interfaces``  
![](img/part3//Screenshot%202024-07-02%20at%202.13.21%20PM.png)  
---
- ``lo - Это внутренний адрес, который направляет обратно в локальную систему.``  
---    
- ``get the ip address from the DHCP server``
![](img/part3/Screenshot%202024-07-02%20at%203.49.58%20PM.png) 
---
``DHCP - Dynamic Host Configuration Protocol``
---
- ``gateway (ip)``  
![](img/part3/Screenshot%202024-07-02%20at%204.02.21%20PM.png)
---
- ``internal IP address of the gateway, aka default ip address (gw)``  
![](img/part3/Screenshot%202024-07-02%20at%204.08.05%20PM.png)  
---
- ``Set static (manually set, not received from DHCP server) ip, gw, dns settings (use public DNS servers, e.g. 1.1.1.1 or 8.8.8.8)``  
![](img/part3/Screenshot%202024-07-02%20at%204.14.39%20PM.png)
![](img/part3/Screenshot%202024-07-02%20at%204.26.14%20PM.png)  
---
- ``заданные настройки соответсвуют``  
![](img/part3/Screenshot%202024-07-02%20at%204.31.24%20PM.png) 
---
- ``Ping 1.1.1.1 & ya.ru``  
![](img/part3/Screenshot%202024-07-02%20at%204.36.16%20PM.png)
## Part 4. OS Update
- `обновили системные пакеты`
---
![](img/part4/Screenshot%202024-07-02%20at%204.44.00%20PM.png)
## Part 5. Using the sudo command
- ``Команда sudo предоставляет возможность пользователям выполнять команды от имени суперпользователя root, либо других пользователей``
---
- `Разрешили созданному пользователю использовать команду sudo, переключились на него и изменили имя хоста`
![](img/part5/Screenshot%202024-07-02%20at%205.02.23%20PM.png)
## Part 6. Installing and configuring the time service
- `Устанавливаем пакет синхронизации времени`
---
![](img/part6/Screenshot%202024-07-02%20at%2017.14.06.png)
- `Добавляем задание в планировщик crontab -e и добавляем туда строку: @daily /usr/sbin/ntpdate pool.ntp.org`
-  `Теперь раз в сутки время само синхронизируется.`
---
![](img/part6/Screenshot%202024-07-02%20at%2017.19.28.png)
## Part 7. Installing and using text editors
- `VIM text_vim.txt вышел из режима insert с помощью ESC, сохранил изменения и вышел с помощью команды :wq`
---
![](img/part7/Screenshot%202024-07-02%20at%2017.39.00.png)
---
- `NANO text_nano.txt для сохранения ^O, для выхода ^X`
---
![](img/part7/Screenshot%202024-07-02%20at%2017.47.51.png)
---
- `JOE text_joe.txt для сохранения и выхода нажал клавиши ^KQ`
---
![](img/part7/Screenshot%202024-07-02%20at%2018.15.43.png)
---
- `VIM вышел без сохранения с помощью команды :q!`
---
![](img/part7/Screenshot%202024-07-02%20at%2018.28.41.png)
---
- `NANO вышел без сохранения с помощью коммнад ^X -> N`
---
![](img/part7/Screenshot%202024-07-02%20at%2018.31.13.png)
---
- `JOE вышел без сохранения с помощью коммнад ^C -> y`
---
![](img/part7/Screenshot%202024-07-02%20at%2018.33.37.png)
---
- `VIM для поиска /что_ищем`
---
![](img/part7/Screenshot%202024-07-02%20at%2018.37.01.png)
---
- `VIM для замены :s/что_меняем/на_что_меняем`
---
![](img/part7/Screenshot%202024-07-02%20at%2018.38.04.png)
---
 - `NANO для поиска: ^W -> что_ищем`
---
![](img/part7/Screenshot%202024-07-02%20at%2019.26.18.png)
---
- `NANO для замены: ^\ -> что_меняем -> на_что_меняем -> Y`
---
![](img/part7/Screenshot%202024-07-02%20at%2019.27.53.png)
--- 
- `JOE для поиска: ^K F -> что ищем -> I`
---
![](img/part7/Screenshot%202024-07-02%20at%2019.18.41.png)
---
- `JOE для замены: ^K F -> что_меняем -> R -> на_что_меняем -> Y`
---
![](img/part7/Screenshot%202024-07-02%20at%2019.20.54.png)
---
## Part 8. Installing and basic setup of the SSHD service
 - `Установка службы sshd`  
![](img/part8/Screenshot%202024-07-02%20at%2019.35.49.png)
---
- `Добавляем сервис в автозагрузку с помощью команды sudo systemctl enable sshd`  
---
- `Перенастроил службу SSHd на порт 2022`  

![](img/part8/Screenshot%202024-07-02%20at%2020.05.53.png)
---
- `команда ps`  
ps - выводит сведения о процессах в статическом виде  
-e - позволяет выбрать все процессы  
| grep sshd - поиск по выводу через пайп  
![](img/part8/Screenshot%202024-07-02%20at%2020.07.42.png)
---

- `перезагрука системы reboot`
- `netstat -tan`
---
![](img/part8/Screenshot%202024-07-02%20at%2020.16.18.png)
---
- `-a - Показывать состояние всех сокетов; обычно сокеты, используемые серверными процессами, не показываются`  
- `-n - Показывать сетевые адреса как числа. netstat обычно показывает адреса как символы`  
- `-t - Отображать TCP подключения`  
- `Proto - Содержит тип протокола`  
- `Recv-Q - Счётчик байтов не скопированных программой пользователя из этого сокета`  
- `Send-Q - Счётчик байтов, не подтверждённых удалённым узлом`  
- `Local Address - Адрес и номер порта локального конца сокета`  
- `Foreign Address - Адрес и номер порта удалённого конца сокета`  
- `State - Состояние сокета`  
- `LISTEN Сокет ожидает входящих подключений`  
- `0.0.0.0 - это немаршрутизируемый адрес IPv4, который используется в качестве адреса по умолчанию или адреса-заполнителя`
## Part 9. Installing and using the top, htop utilities
- `uptime: 33min`
- `number of authorised users: 1 user`
- `total system load: 0.00, 0.00, 0.00`
- `total number of processes: 106 total`
- `cpu load: 0.0 us, 0.2 sy, 0.0 ni, 100.0 id, 0.0 wa, 0.0 hi, 0.0 si, 0.0 st`
- `memory load: 964.9 total, 251.4 free, 189.7 used, 523.8 buff/cache`
- `pid of the process with the highest memory usage: PID 938`
- `pid of the process taking the most CPU time: PID 938`
---
- `sorted by PID`
![](img/part9/Screenshot%202024-07-03%20at%2014.48.30.png)
- `sorted by PERCENT_CPU`
![](img/part9/Screenshot%202024-07-02%20at%2021.01.19.png)
- `sorted by PERCENT_MEM`
![](img/part9/Screenshot%202024-07-02%20at%2021.01.40.png)
- `sorted by TIME`
![](img/part9/Screenshot%202024-07-02%20at%2021.01.52.png)
- `filtered for sshd process`
![](img/part9/Screenshot%202024-07-02%20at%2021.05.31.png)
- `with the syslog process`
![](img/part9/Screenshot%202024-07-02%20at%2021.08.15.png)
- `with hostname, clock and uptime`
- ![](img/part9/Screenshot%202024-07-03%20at%2014.40.58.png)
## Part 10. Using the fdisk utility
- `Disk /dev/sda: 16 Gib, 17179869184 bytes, 33554432 sectors`
![](img/part10/Screenshot%202024-07-03%20at%2015.05.48.png)
- `size of swap`
![](img/part10/Screenshot%202024-07-03%20at%2015.08.04.png)
## Part 11. Using the df utility
- `команда df /`
---
- `размер раздела 16400252 bytes`
- `размер занятого пространства 6406540 bytes`
- `размер свободного пространства 9138624 bytes`
- `процент использования 42%`
---
- `команда df -Th /`
- `размер раздела 16G`
- `размер занятого пространства 6.2G`
- `размер свободного пространства 8.8G`
- `процент использования 42%`
- `тип файловой системы ext4`
## Part 12. Using the du utility
- `/home`
![](img/part12/Screenshot%202024-07-03%20at%2015.34.18.png)
---
- `/var`
![](img/part12/Screenshot%202024-07-03%20at%2015.34.38.png)
---
- `/var/log`
![](img/part12/Screenshot%202024-07-03%20at%2015.34.59.png)
---
- `/var/log/*`
![](img/part12/Screenshot%202024-07-03%20at%2015.35.40.png)
## Part 13. Installing and using the ncdu utility
- `Установка ncdu`
![](img/part13/Screenshot%202024-07-03%20at%2015.42.25.png)
---
- `/home`
![](img/part13/Screenshot%202024-07-03%20at%2015.43.16.png)
---
- `/var`
![](img/part13/Screenshot%202024-07-03%20at%2015.43.51.png)
---
- `/var/log`
![](img/part13/Screenshot%202024-07-03%20at%2015.44.23.png)
## Part 14. Working with system logs
- `время последней успешной авторизации, имя пользователя и метод входа в систему`
![](img/part14/Screenshot%202024-07-03%20at%2015.56.17.png)
---
- `Перезапуск службы SSHd`
![](img/part14/Screenshot%202024-07-03%20at%2015.58.52.png)
---
## Part 15. Using the CRON job scheduler
- `Добавляем в планировщик заданий команду uptime через каждые 2 минуты`  
![](img/part15/Screenshot%202024-07-03%20at%2017.00.49.png)
---
- `uptime каждые 2 минуты`  
![](img/part15/Screenshot%202024-07-03%20at%2017.14.57.png)
---
- `список задач`  
![](img/part15/Screenshot%202024-07-03%20at%2017.03.55.png)
---
- `Удалил все задания из планировщика заданий`  
![](img/part15/Screenshot%202024-07-03%20at%2017.07.57.png)