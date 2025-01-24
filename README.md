
## Используемые технологии

- **Java 17**: Основной язык разработки
- **Spring Boot 3.4.1**: Фреймворк для разработки приложений
- **Spring Cloud Config Server**: Для централизованного управления конфигурациями
- **Docker**: Контейнеризация приложения
- **Gradle**: Система сборки

## Установка

### Системные требования

- **Java 17**
- **Gradle 8.13-milestone-3** (уже установлен в Docker-образе)
- **Docker** для контейнеризации
- 
1. Клонируйте репозиторий:

   ```bash
   git clone https://github.com/macygabr/ConfigServer.git
   ```

2. Соберите и запустите приложение:

   ```bash
   cd ConfigServer
   docker build -t config-server .
   docker run -p 8888:8888 config-server
   ```