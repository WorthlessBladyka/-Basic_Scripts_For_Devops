==**Docker Compose**== — это инструмент для управления многоконтейнерными приложениями Docker. Он позволяет определить и запускать все сервисы (контейнеры) приложения, такие как базы данных, серверы и другие компоненты, с помощью одного файла конфигурации в формате YAML.

!docker-compose.yuml / .yml

![[Screenshot_26.png]]
![[Screenshot_29.png]]

```                                                            --link
$ docker run -d --name=redis redis

$docker run -d --name-vote -p 5000:80 --link redis:redis voting-app

		#--link вносит статическую запись в /etc/hosts контейнера vote 
		# с привязкой имени redis к текущему внутреннему ip контейнера redis
		
		#--link устаревшая option за место него есть другие options
		#redis:redis
```
![[Screenshot_25.png]]
![[Screenshot_28.png]]
``` 
docker-compose up
			#Поднять стек
```


## Docker-compose build 
![[Screenshot_30.png]]
!Docker-compose up сначала соберет image из build, а потом с помощью него поднимет контейнер.


## Docker-compose versions
![[Screenshot_31.png]]
!v1 есть ограничения, невозможно развернуть контейнеры в другой сети, отличный от хостовой сети по умолчанию.
!v1 невозможно указать, что один контейнер зависит от запуска другого.

!v2 информацию о стеке теперь указывается в разделе "services"
!v2 вводит ф-ию зависимости для запуска "depends_on", если нужно указать порядок запуска контейнеров

!v3 ее структура сходна с version_2
!v3 отличие от version_2 поддержка аркистрации с помощью docker ском и специфические возможности для совместной работы нескольких хостов. В ней некоторые возможности были удалены и некоторые добавлены.

## Docker-compose voting application

До сих пор, мы развертывали контейнеры в мостовой сети по умолчанию, хорошей практикой считается разделить трафик из разных источников.
![[Screenshot_32.png]]
Для этого, мы создаем внешнюю сеть для трафика пользователей и внутреннюю для общения между приложениями (frontend and backend).

```
version:2

services:
  redis:
  networks:
    - backend

networks:
  frontend:
  backend:
```

## Command

``` run
$ docker-compose up -d
```
```stop_steck_and_rm_all_conteners
$ docker-compose down
```
```
$ docker-compose ps
		#отобразит за какие контейнеры docker-compose несет ответственность
```
```
$ docker-compose logs
		#общий pull logs
```

```
docker-compose up -d --scale cote=3
		#управление реплик определенной службы
```

### --scale
```
$ docker-compose up --scale counter=2
		#Запускает несколько инстансов (контейнеров) указанного сервиса
		#Инстанс сервиса — это конкретный запущенный экземпляр (контейнер)
		#сервиса, описанного в docker-compose.yml.
```
```
		# Не должно быть указано ports: "8080:8080" (статический порт)
	    # Должно быть: ports: "8080" или ports: "8080-8090"
    ports:
      - "8080"  
		        # ДИНАМИЧЕСКИЙ порт (работает)
				# ИЛИ диапазон портов:
    ports:
      - "8080-8090"
        
- "8080:8080"  # СТАТИЧЕСКИЙ порт - ошибка при масштабировании!
```

### 11111111 MAIN
```
docker compose --file ~/.config/winapps/compose.yaml start # Power on the Windows VM
docker compose --file ~/.config/winapps/compose.yaml pause # Pause the Windows VM
docker compose --file ~/.config/winapps/compose.yaml unpause # Resume the Windows VM
docker compose --file ~/.config/winapps/compose.yaml restart # Restart the Windows VM
docker compose --file ~/.config/winapps/compose.yaml stop # Gracefully shut down the Windows VM
docker compose --file ~/.config/winapps/compose.yaml kill # Force shut down the Windows VM
```
###