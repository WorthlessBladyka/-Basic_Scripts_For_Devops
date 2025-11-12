# Edit name server

``` edits_names
$ sudo nano /etc/hostname

$ sudo nano /etc/hosts
```

# Static IP

``` old_metod
$ ip addr               # смотрим наше название порта

$ sudo nano /etc/network/interfaces       #дописываем в файл
	auto enp0s3
	iface enp0s3 inet static
		address 20.20.20.20
		netmask 255.0.0.0
		gateway 20.20.20.1
		dns-nameservers 8.8.8.8
		
$ sudo ifdown enp0s3            #перезагружаем интерфейс
$ sudo ifup enp0s3
```

```
$ cd /etc/netplan/<configFile.yaml>
			# Открываем и редактируем, шаблон берем с gitHub

$ sudo chmod 600 <configFile.yaml>
$ sudo netplan apply

```