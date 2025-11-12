!В продакшене используют частные docker registry

![[Снимок экрана 2025-10-30 в 3.37.48 PM.png]]

![[Снимок экрана 2025-10-30 в 3.39.20 PM.png]]
![[Снимок экрана 2025-10-30 в 3.41.22 PM.png]]
docker.io
gcr.io

```http_connect
client:
# nano /etc/docker/daemon.json
"insecure-registries": ["192.1.1.25:5000"]
ctrl+x yes
		#docker из коробки не готов работать с not secure connect.
sudo systemctl daemon-reload
sudo systemctl restart docker

docker build . -t 10.221.12.2:5000/apache2
docker push 10.221.12.2:5000/apache2
docker pull 10.221.12.2:5000/apache2
```

```https + самоподписанный сертификат
генерируем приватный ключ и сертификат



```