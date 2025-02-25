# Config Server

## О проекте

**Config Server** – это централизованный сервис для хранения и управления конфигурационными файлами других сервисов. Он позволяет динамически изменять настройки приложений без их перезапуска, обеспечивая удобное управление конфигурациями в распределенных системах.

## Используемые технологии

- **Java 17**: основной язык разработки
- **Spring Boot 3.4.1**: фреймворк для разработки приложений
- **Spring Cloud Config Server**: централизованное управление конфигурациями
- **Docker**: контейнеризация приложения
- **Gradle**: система сборки

## Установка

### Системные требования

- **Java 17**
- **Gradle 8.13-milestone-3** (уже установлен в Docker-образе)
- **Docker** (для контейнеризации)

### Установка и запуск

1. **Клонируйте репозиторий**:

   ```bash
   git clone https://github.com/macygabr/ConfigServer.git
   cd ConfigServer
   ```

2. **Соберите и запустите приложение в контейнере:**:

   ```bash
   docker build -t config-server .
   docker run -p 8888:8888 config-server
   ```
### Конфигурация:
   1. **В файле application.properties укажите URL репозитория с конфигурациями:**
   ```bash
   spring.cloud.config.server.git.uri=url-to-your-repository
   ```
   2. **Если репозиторий приватный, добавьте аутентификационные данные:**
   ```bash
spring.cloud.config.server.git.username=your-username
   spring.cloud.config.server.git.password=your-token
   ```
### API:
   **Получение конфигурации для сервиса app1 в профиле dev:**

   ```bash
   curl http://localhost:8888/app1/dev
   ```