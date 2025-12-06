## Установка ssh
```check_status_ssh
$ service ssh status
			#ubuntu
$ systemctl status ssh
			#debian
```

``` download_SSH
$ sudo apt-get install openssh-server
```

```
$ service ssh start
```

## Generator key 
```
# ssh-keygen -t rsa
```
## Generation certificat
```
# Минимальная команда для localhost
mkdir -p certs
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
  -keyout certs/domain.key -out certs/domain.crt \
  -subj '/CN=localhost'
```
- openssl - утилита для работы с криптографией
- req - субкоманда для работы с запросами сертификатов (Certificate Signing Requests)
- X509 - стандарт для инфраструктуры открытых ключей (генерировать самоподписанный сертификат вместо запроса на подпись)
- SHA-256 - Алгоритм хеширования для подписи сертификата
- No DES - не шифровать приватный ключ (- Ключ будет сохранен без пароля (в открытом виде)
- - **`-newkey`** - создать новый ключ
- - **`rsa:2048`** - алгоритм RSA с длиной ключа 2048 бита
- keyout privateKey.key - приватного ключа
- out certificate.crt - сохранения сертификата
## Connect linux

``` connect
# ssh user@192.168.1.3     # ssh пользователь_на_серверной_машине@IP_server
```

## Connect windows

[download_putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
[download_mobaXterm](https://mobaxterm.mobatek.net/download.html)

## Connect MacOS

