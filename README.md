# che-cloud-v2

## Components

  - traefik:v1.4.2
  - eclipse/che-server-multiuser:5.20.0
  - postgres:9.6
  - jboss/keycloak-openshift:3.4.0.Final

#### Подготовка

Перед развертыванием системы запусите из корня проекта скрипт:

```sh
./prepare.sh
```

#### Запуск системы

```sh
docker-compose down && docker-compose up
```

#### Взаимодействие с системой

|сервис         | контекстный путь |
| ------------- | ---------------- |
| eclipse-che   | /                |
| keycloak      | /auth            |


#### Протестированное окружение
|ОС                 | docker                   |docker-compose       |
| ------------------| -------------------------|---------------------|
| Ubuntu 16.04.1 LTS| 17.06.2-ce, build cec0b72|1.16.1, build 6d1ac21|

#### Настройка keycloak
- перейдите на url /auth
- стандартный логин/пароль : admin/admin
- В левом углу выберите Che
- Clients -> che-public
- Пропишите Ваш public-IP в **Valid Redirect URIs** и **Web Origins**
- Нажмите Save внизу страницы

## Литература
#### Docker
[Развертывание сервисов через *.yml файлы](http://training.play-with-docker.com/traefik-load-balancing/)

[Типы labels в swarm](https://docs.docker.com/engine/reference/commandline/service_create/#specify-service-constraints-constraint)


#### Мониторинг
[Репозиторий](https://github.com/botleg/swarm-monitoring.git)

[Настройка сервисов мониторинга swarm кластера](https://habrahabr.ru/company/southbridge/blog/327670/)