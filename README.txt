Название проекта: Culture Events

Описание проекта
Culture Events — это веб-приложение на Java (Spring Boot), предназначенное для отображения, хранения и управления культурными событиями, формирующее пользовательские рекомендации в ответ на POST запрос.
Проект включает пользовательскую часть, интеграцию с PostgreSQL, а также возможность развёртывания через Docker.

Технологии
Java 17
Spring Boot
Spring Web
Spring Data JPA
PostgreSQL
Hibernate
Lombok
Docker и Docker Compose
Maven

Структура проекта
project-root/
src/
main/
java/…
resources/
application.yaml
static / templates
test/
Dockerfile
docker-compose.yml
pom.xml
README.txt

Конфигурация
Основные настройки расположены в файле application.yaml.

Подключение к базе данных:
spring:
datasource:
url: jdbc:postgresql://localhost:5432/cultureevents
username: postgres
password: culture
driver-class-name: org.postgresql.Driver
jpa:
hibernate:
ddl-auto: validate
show-sql: true
properties:
hibernate:
dialect: org.hibernate.dialect.PostgreSQLDialect
format_sql: true

Инструкция по запуску
 1. Локальный запуск
Выполнить команду:
mvn spring-boot:run
Приложение будет доступно по адресу:
http://localhost:8080
 2. Запуск через Docker
Сборка образа:
docker build -t culture-events .
Запуск контейнера:
docker run -p 8080:8080 culture-events
 3. Запуск через Docker Compose
docker compose up –build
Этот вариант запускает приложение и базу данных одновременно.

Пример API
POST /api/events/recommendations
GET /api/debug/events

Команда проекта
Никита - backend, lead
Артем - frontend
Алиса - algorithms