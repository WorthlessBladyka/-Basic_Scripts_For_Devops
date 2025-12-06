1) Освоить и вспомнить базовый linux
2) Изучить и написать 3 скрипта на bash
3) Скачать и освоить docker
4) 5) Python выучить основы и тренироваться на тренажерах
5) Далее k8s
6) Написать на python бота в tg
7) CI/CD

| Category                         | Technologies                                                                                                                                                                                                                                                                                                                                       | Level                                                           |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| **Cloud Platforms**              | ![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white) ![GCP](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)![Azure](https://img.shields.io/badge/Microsoft_Azure-0089D6?style=for-the-badge&logo=microsoft-azure&logoColor=white)            | ![Advanced](https://img.shields.io/badge/Advanced-green)        |
| **Containerization**             | ![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)                                                                                                                            | ![Advanced](https://img.shields.io/badge/Advanced-green)        |
| **IaC & Config Management**      | ![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white) ![Ansible](https://img.shields.io/badge/Ansible-000000?style=for-the-badge&logo=ansible&logoColor=white) ![CloudFormation](https://img.shields.io/badge/CloudFormation-FF9900?style=for-the-badge)                                  | ![Advanced](https://img.shields.io/badge/Advanced-green)        |
| **CI/CD & DevOps Tools**         | ![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white) ![GitLab CI](https://img.shields.io/badge/GitLab_CI-FC6D26?style=for-the-badge&logo=gitlab&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white) | ![Advanced](https://img.shields.io/badge/Advanced-green)        |
| **Monitoring & Logging**         | ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white) ![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white) ![ELK Stack](https://img.shields.io/badge/ELK_Stack-005571?style=for-the-badge&logo=elastic&logoColor=white)            | ![Intermediate](https://img.shields.io/badge/Intermediate-blue) |
| **Scripting & Programming**      | ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) ![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white) ![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)                                                | ![Intermediate](https://img.shields.io/badge/Intermediate-blue) |
| **Linux & OS**                   | ![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black) ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white) ![CentOS](https://img.shields.io/badge/CentOS-262577?style=for-the-badge&logo=centos&logoColor=white)                                     | ![Advanced](https://img.shields.io/badge/Advanced-green)        |
| **Networking & Security**        | ![VPN](https://img.shields.io/badge/VPN-4A154B?style=for-the-badge) ![Firewall](https://img.shields.io/badge/Firewall-FF6B35?style=for-the-badge) ![SSL/TLS](https://img.shields.io/badge/SSL/TLS-3D8FCC?style=for-the-badge)                                                                                                                      | ![Intermediate](https://img.shields.io/badge/Intermediate-blue) |
| **Databases**                    | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white) ![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)                            | ![Intermediate](https://img.shields.io/badge/Intermediate-blue) |
| **Service Mesh & Orchestration** | ![Istio](https://img.shields.io/badge/Istio-466BB0?style=for-the-badge&logo=istio&logoColor=white) ![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=helm&logoColor=white)                                                                                                                                                 | ![Beginner](https://img.shields.io/badge/Beginner-yellow)       |
|                                  |                                                                                                                                                                                                                                                                                                                                                    |                                                                 |


# lINUX
1. **Терминал — ваш лучший друг:**
    
    - Поймите, почему командная строка (CLI) — это главный инструмент администратора.
        
    - Основы навигации: `pwd`, `ls`, `cd`, `mkdir`, `touch`, `cp`, `mv`, `rm`.
        
    - Работа с файлами: `cat`, `less`, `head`, `tail`, `nano` (простейший текстовый редактор).
        
2. **Справочная система:**
    
    - Команда `man` (manual) — ваш главный справочник. Учитесь ей пользоваться.
        
    - Команда `--help` или `-h` для быстрой справки.
        

**Практика:** Установите Ubuntu в VirtualBox. Создайте структуру папок (`/home/yourname/projects/test_project/`) и поработайте с файлами исключительно через терминал.

---

### **Этап 1: Базовое администрирование (Недели 5-12)**

**Цель:** Научиться управлять системой, пользователями и процессами.

1. **Файловая система и права доступа:**
    
    - Структура каталогов Linux (`/`, `/home`, `/etc`, `/var`, `/tmp` и т.д.).
        
    - Права доступа: `chmod` (изменение прав), `chown` (изменение владельца), `chgrp` (изменение группы). Понимание `rwx` для user/group/other.
        
2. **Управление пользователями и группами:**
    
    - Команды: `useradd`, `usermod`, `userdel`, `groupadd`, `passwd`.
        
    - Понимание файлов `/etc/passwd`, `/etc/group`, `/etc/shadow`.
        
3. **Управление процессами:**
    
    - Просмотр процессов: `ps`, `top`, `htop`.
        
    - Завершение процессов: `kill`, `killall`, `pkill`.
        
    - Запуск процессов в фоне (`&`) и управление заданиями (`jobs`, `fg`, `bg`).
        
4. **Управление пакетами:**
    
    - Менеджеры пакетов: `apt` (Debian/Ubuntu) или `yum`/`dnf` (RedHat/CentOS).
        
    - Обновление системы, поиск, установка и удаление ПО.
        
5. **Редакторы для продвинутых:**
    
    - **Vim** или **Nano**. Vim имеет крутую кривую обучения, но это мощнейший инструмент. Начните с `vimtutor`.
        
6. **Сетевые основы:**
    
    - Команды: `ip addr` (или устаревший `ifconfig`), `ping`, `ss` (или `netstat`).
        
    - Настройка статического IP-адреса и DNS.
        

**Практика:**

1. Создайте нового пользователя, добавьте его в группу `sudo`.
    
2. Установите какой-нибудь пакет (например, `htop`) и попрактикуйтесь в его использовании.
    
3. Создайте сценарий, который меняет владельца и права для папки с веб-документами (например, `chown -R www-data:www-data /var/www/html` и `chmod -R 755 /var/www/html`).
    

---

### **Этап 2: Ключевые навыки сисадмина (Недели 13-24)**

**Цель:** Освоить инструменты, без которых не обходится ни один день работы.

1. **Суперпользователь (root):**
    
    - Команда `sudo` и конфигурационный файл `/etc/sudoers`. Никогда не работайте под root постоянно!
        
2. **Мониторинг и логи:**
    
    - Чтение и анализ логов в `/var/log/` (особенно `syslog`, `auth.log`).
        
    - Использование `journalctl` (для систем на base systemd).
        
    - Мониторинг ресурсов: `df`, `du`, `free`, `iostat`.
        
3. **Управление загрузкой и системными сервисами:**
    
    - Системный менеджер `systemd`.
        
    - Команды: `systemctl start/stop/restart/enable/status` для управления службами (например, `ssh`, `nginx`).
        
4. **Работа с дисками:**
    
    - Файловые системы (ext4, XFS).
        
    - Команды: `fdisk`/`cfdisk`, `mkfs`, `mount`.
        
    - Настройка автоматического монтирования в `/etc/fstab`.
        
5. **Планировщик заданий `cron`:**
    
    - Создание и редактирование заданий (`crontab -e`).
        
    - Системные cron-задачи в `/etc/cron.*/`.
        
6. **Сетевые службы:**
    
    - Установка и настройка SSH-сервера. Ключевая аутентификация вместо паролей.
        
    - Основы настройки веб-сервера (Nginx или Apache) и фаервола (`ufw` или `iptables`).
        

**Практика:**

1. Настройте SSH-сервер на виртуальной машине и подключитесь к ней с хостовой машины.
    
2. Добавьте cron-задачу, которая будет каждую ночь создавать резервную копию вашей домашней директории в виде архива.
    
3. Добавьте новый диск в виртуальную машину, отформатируйте его в ext4 и настройте автоматическое монтирование в папку `/mnt/data`.
    

---

### **Этап 3: Продвинутые темы и специализация (Недели 25+)**

**Цель:** Готовность к работе в реальной среде.

1. **Скриптование:**
    
    - **Bash-скрипты!** Это обязательный навык. Учите условия (`if`), циклы (`for`, `while`), функции и работу с параметрами.
        
    - Автоматизация рутинных задач (бэкапы, мониторинг, деплой).
        
2. **Резервное копирование:**
    
    - Инструменты: `tar`, `rsync`. Стратегии бэкапов (полные, инкрементальные).
        
3. **Виртуализация и контейнеризация:**
    
    - **Docker.** Это must-have в современном мире. Учитесь создавать `Dockerfile`, запускать контейнеры, работать с Docker Compose.
        
    - Позже можно изучить оркестрацию (Kubernetes).
        
4. **Системы управления конфигурациями (IaC - Infrastructure as Code):**
    
    - **Ansible.** Позволяет автоматизировать настройку десятков и сотен серверов. Начните с него, он самый простой для входа.
        
5. **Централизованное логирование и мониторинг:**
    
    - Знакомство с такими стеками, как ELK/EFK (для логов) и Prometheus + Grafana (для метрик и мониторинга).
        
6. **Безопасность:**
    
    - Основы `iptables`/`nftables` (файрволы).
        
    - Аудит безопасности с помощью `fail2ban`.
        
    - Концепция SELinux/AppArmor (на продвинутом уровне).
        

**Практика:**

1. Напишите bash-скрипт, который проверяет место на диске и при его заполнении более чем на 90% отправляет вам письмо (можно просто выводить сообщение в лог).
    
2. Установите Docker и запустите контейнер с Nginx, "пробросив" порт на хост-систему.
    
3. Напишите простой Ansible-плейбук, который устанавливает Nginx и копирует ваш простой HTML-сайт на несколько виртуальных машин.