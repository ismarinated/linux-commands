<h2>Part 1. Установка ОС</h2>

- Вывод выполнен при помощи команды `cat /etc/issue`

![Alt text](templates/task_1.png "Task One")
---

<h2>Part 2. Создание пользователя</h2>

- Пользователь создается командой `sudo useradd -g groupname UserAdm`

![Alt text](templates/task_2_1.png "Task Two")

- Отображение пользователя возможно при использовании команды `cat /etc/passwd`

![Alt text](templates/task_2_2.png "Task Two")
---
<h2>Part 3. Настройка сети ОС</h2>

- Задание имени машины вида user-1 `sudo hostnamectl set-hostname user-1`
- Отображение заданного имени командой `cat /etc/hostname`

![Alt text](templates/task_3_1.png "Task Three")

- Установка временной зоны, соответствующей местоположению, командой `sudo timedatectl set-timezone Europe/Moscow`

- Отображение установленной временной зоны командой `timedatectl`

![Alt text](templates/task_3_2.png "Task Three")

- Вывод названия сетевых интерфейсов выполнен командой `ls /sys/class/net`

- Интерфейс lo (loopback) — это виртуальный сетевой интерфейс для локальной связи внутри устройства

![Alt text](templates/task_3_3.png "Task Three")

- Получение IP-адреса текущего устройства выполнено командой `sudo dhclient -v`

DHCP (Dynamic Host Configuration Protocol) - это сетевой протокол, который позволяет автоматически назначать подключаемым к сети устройствам IP-адреса и другие параметры конфигурации

- 10.0.2.15 - это IP-адрес, который устройство получило от DHCP-сервера
- 10.0.2.2 - IP-адрес DHCP-сервера

![Alt text](templates/task_3_4.png "Task Three")

- Получение внешнего IP-адреса шлюза (ip) выполнено командой `wget -qO- eth0.me`

![Alt text](templates/task_3_5.png "Task Three")

- Получение внутреннего IP-адреса шлюза, он же ip-адрес по умолчанию (gw)

![Alt text](templates/task_3_6.png "Task Three")

- Задание статичных настроек ip, gw, dns выполнено в редакторе vim в конфишурационном файле `/etc/netplan/00-installer-config.yaml`

![Alt text](templates/task_3_7.png "Task Three")
![Alt text](templates/task_3_8.png "Task Three")

- Изменения применены командой `netplan apply` и выполнена перезагрузка устройства командой `reboot`. Для проверки корректности сохранения сетевых настроек выполнены команды `ip addr show`, `ip route show`

![Alt text](templates/task_3_9.png "Task Three")

- Пропингованы удаленные хосты 1.1.1.1 и ya.ru

![Alt text](templates/task_3_10.png "Task Three")
---

<h2>Part 4. Обновление ОС</h2>

- Обновление списка доступных пакетов до последней на момент выполнения задания версии выполнено командой `sudo apt-get update`. Также выполнено обновление всех установленных пакетов командой `sudo apt-get upgrade`
- При повторном выполнении команд выполнения обновлений не происходит

![Alt text](templates/task_4.png "Task Four")
---

<h2>Part 5. Использование команды sudo</h2>

Команда sudo (Super User DO) позволяет выполнять команды от имени суперпользователя (root) или другого пользователя с повышенными привилегиями

- Предоставление созданному пользователю `UserAdm` прав на выполнение команды `sudo` выполнено командой `usermod -aG sudo UserAdm`
- Переключение в сессию `UserAdm` выполнено командой `su Username`
- После перехода убедимся в его корректности при помощи команды `whoami`
- Изменение hostname ОС на `user-2` выполнено в соответствии с Part 3

![Alt text](templates/task_5.png "Task Five")
---

<h2>Part 6. Установка и настройка службы времени</h2>

- Настройка службы автоматической синхронизации времени выполнена при помощи команды `timedatectl`
- Вывод произведенных командой `timedatectl show`

![Alt text](templates/task_6.png "Task Six")
---

<h2>Part 7. Установка и использование текстовых редакторов</h2>

- Для выполнения задания выбраны текстовые редакторы VIM, NANO, MCEDIT.
- Создан файл test_vim.txt для работы в редакторе VIM командой `vim test_vim.txt`, где указан никнейм. Выход из режима редактирова - `esc`, выход с сохранением - `:wq`.

![Alt text](templates/task_7_1.png "Task Seven")

- Создан файл test_nano.txt для работы в редакторе NANO командой `nano test_vim.txt`, где указан никнейм. Выход с сохранением - `Ctrl+o`, `Ctrl+x`.

![Alt text](templates/task_7_2.png "Task Seven")

- Создан файл test_mcedit.txt для работы в редакторе MCEDIT командой `mcedit test_mcedit.txt`, где указан никнейм. Выход с сохранением - `F2`, `F10`.

![Alt text](templates/task_7_3.png "Task Seven")

- Переход в режим редактирования в редакторе VIM - `i`. Выход из режима редактирова - `esc`, выход с сохранением - `:q!`.

![Alt text](templates/task_7_4.png "Task Seven")

- Редактирование файла в NANO выполняется сразу же после открытия. Выход с сохранением - `Ctrl + X`.

![Alt text](templates/task_7_5.png "Task Seven")

- Редактирование файла в MCEDIT выполняется сразу же после открытия. Выход с сохранением - `F10`.

![Alt text](templates/task_7_6.png "Task Seven")

- После изменения строки в редакторе VIM поиск слова по содержимому файла - `/[слово]`

![Alt text](templates/task_7_7.png "Task Seven")

- Замена в VIM - `/[поиск]/[замена]`

![Alt text](templates/task_7_8.png "Task Seven")

- После изменения строки в редакторе NANO поиск слова по содержимому файла - `Ctrl + W`

![Alt text](templates/task_7_9.png "Task Seven")

- Замена в NANO - `Ctrl + \`

![Alt text](templates/task_7_10.png "Task Seven")

![Alt text](templates/task_7_11.png "Task Seven")

![Alt text](templates/task_7_12.png "Task Seven")

- После изменения строки в редакторе MCEDIT поиск слова по содержимому файла - `F7`

![Alt text](templates/task_7_13.png "Task Seven")

![Alt text](templates/task_7_14.png "Task Seven")

- Замена в MCEDIT - `F4`

![Alt text](templates/task_7_15.png "Task Seven")

![Alt text](templates/task_7_16.png "Task Seven")
---

<h2>Part 8. Установка и базовая настройка сервиса SSHD</h2>

- Установка службы SSHd выполнена путем установки утилит openssh-server и ssh

![Alt text](templates/task_8_1.png "Task Eight")

- Добавление автостарта службы при загрузке системы выполнено командой `sudo systemctl enable ssh`

![Alt text](templates/task_8_2.png "Task Eight")

- Перенастройка службы SSHd на порт 2022 выполнена в редакторе VIM

![Alt text](templates/task_8_3.png "Task Eight")

- Для принятия изменений выполнен перезапуск SSHd командой `systemctl restart sshd`

![Alt text](templates/task_8_4.png "Task Eight")

- Для отображения сетевых соединений, где фигурирует порт 2022, выполнена команда `netstat -tan`

![Alt text](templates/task_8_5.png "Task Eight")

Значение ключей `-tan`: `-t` - отображение только TCP соединений, `-a` - отображение всех соединений и портов, `-n` - вывод IP-адресов и портов в числовом формате.

Значение столбцов: `Proto` - протокол соединения, `Recv-Q` (Receive Queue) - количество запросов в очередях на приём на данном устройстве, `Send-Q` (Send Queue) - количество запросов в очередях на отправку на данном устройстве, `Local Address` - IP-адрес и порт на устройстве, который слушает соединение, `Foreign Address` - IP-адрес и порт удалённого подключения, `State` - текущее состояние соединения.

`0.0.0.0:*` означает, что служба принимает соединения с любого адреса и любого порта

- Для отображения процесса sshd использована команда `ps aux | grep sshd`

![Alt text](templates/task_8_6.png "Task Eight")

Значение ключей: `a` - отображение всех процессов кроме фоновых, `u` - отображение процессов пользователя, `x` - отображение процессов, отсоединенных от терминала.

- Для перезагрузки системы использована команда `sudo reboot`
---

<h2>Part 9. Установка и использование утилит top, htop</h2>

Запуск утилиты `top`

![Alt text](templates/task_9_1.png "Task Nine")

- uptime - 1:20
- количество авторизованных пользователей - 1
- средняя загрузка системы
![Alt text](templates/task_9_2.png "Task Nine")
- общее количество процессов
![Alt text](templates/task_9_3.png "Task Nine")
- загрузку cpu
![Alt text](templates/task_9_4.png "Task Nine")
- загрузку памяти
![Alt text](templates/task_9_5.png "Task Nine")
- pid процесса занимающего больше всего памяти - 1
- pid процесса, занимающего больше всего процессорного времени - 1778, 2268, 2283

Запуск утилиты `htop`

- отсортированному по PID
![Alt text](templates/task_9_6.png "Task Nine")
- отсортированному по PERCENT_CPU
![Alt text](templates/task_9_7.png "Task Nine")
- отсортированному по PERCENT_MEM
![Alt text](templates/task_9_8.png "Task Nine")
- отсортированному по TIME
![Alt text](templates/task_9_9.png "Task Nine")
- отфильтрованному для процесса sshd
![Alt text](templates/task_9_10.png "Task Nine")
- с процессом syslog, найденным, используя поиск
![Alt text](templates/task_9_11.png "Task Nine")
с добавленным выводом hostname, clock и uptime
![Alt text](templates/task_9_12.png "Task Nine")
---

<h2>Part 10. Использование утилиты fdisk</h2>

![Alt text](templates/task_10_1.png "Task Ten")

- название жесткого диска - /dev/mapper/ubuntu--vg-ubuntu--lv
- размер - 8,25 GiB, 8854175744 bytes
- количество секторов - 17293312
- размер swap (не отображен в выводе, для него использована команда `free -h`)
![Alt text](templates/task_10_2.png "Task Ten")
---

<h2>Part 11. Использование утилиты df</h2>

Запуск утилиты `df`

![Alt text](templates/task_11_1.png "Task Eleven")

- размер раздела - 8408452
- размер занятого пространства - 4565632
- размер свободного пространств - 3394104
- процент использования - 58%
- единица измерения в выводе - Кб

Запуск утилиты `df -Th`

![Alt text](templates/task_11_2.png "Task Eleven")

- размер раздела - 8,1 Гб
- размер занятого пространства - 4,4 Гб
- размер свободного пространств - 3,3 Гб
- процент использования - 58%
- тип файловой системы для раздела - ext4
---

<h2>Part 12. Использование утилиты du</h2>

- Запуск команды `du`

![Alt text](templates/task_12_1.png "Task Twelve")

- Вывод размеров папок /home, /var, /var/log в байтах выполнен с помощью команды `sudo du -sh /home /var /var/log`

![Alt text](templates/task_12_2.png "Task Twelve")

- Вывод размеров всего содержимого в /var/log выполнен с помощью команды `sudo du -sh /var/log/*`

![Alt text](templates/task_12_3.png "Task Twelve")
---

<h2>Part 13. Установка и использование утилиты ncdu</h2>

- Установка утилиты `ncdu` выполнена командой `sudo apt-get install ncdu`

![Alt text](templates/task_13_1.png "Task Thirteen")

- Вывод размеров папки /home выполнен командой `sudo ncdu /home`

![Alt text](templates/task_13_2.png "Task Thirteen")

- Вывод размеров папки /home выполнен командой `sudo ncdu /var`

![Alt text](templates/task_13_3.png "Task Thirteen")

- Вывод размеров папки /home выполнен командой `sudo ncdu /var/log`

![Alt text](templates/task_13_4.png "Task Thirteen")
---

<h2>Part 14. Работа с системными журналами</h2>

![Alt text](templates/task_14_1.png "Task Fourteen")

- время последней успешной авторизации - 19:22:58
- имя пользователя - fondapho
- метод входа в систему - LOGIN

Перезапуск службы SSHd

![Alt text](templates/task_14_2.png "Task Fourteen")
---

<h2>Part 15. Использование планировщика заданий CRON</h2>

- Для открытия и изменения планировщика заданий использована команда `crontab -e`

![Alt text](templates/task_15_1.png "Task Fifteen")

- Для отображения список текущих заданий для CRON использована команда `crontab -l`

![Alt text](templates/task_15_2.png "Task Fifteen")

- Выполнение задач

![Alt text](templates/task_15_3.png "Task Fifteen")

- Удаление всех заданий из планировщика выполнено командой `crontab -r`

![Alt text](templates/task_15_4.png "Task Fifteen")