##### sudo apt autoremove
!Удаляет неиспользуемые зависимости пакетов
##### cd /tmp && rm *
!Удаляет все временные файлы
##### sudo apt clean
!Удаляет кэш скаченных пакетов

# Monitoring system
##### date - время и дата
``` basic_return_data_and_time
$ date
```

``` set_data_and_time
$ sudo date -s "2024-09-26 12.00:00"
```

##### top and htop - системный монитор
htop -цветной, информативный, ветки процессов, управление мышью
##### free - RAM

##### df and du - дисковое пространство

##### uname -a

# Work_with_packets
``` shell
		# просмотр версии пакета
$ apt show <name package>
```

``` shell
		# выводит лист установленных пакетов
$ dpkg -l
```
