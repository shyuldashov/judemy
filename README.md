# JUdemy

## Описание проекта:

- Цифровая образовательная платформа

---

## Стек технологий:

- JDBC
- Servlet
- PostgreSQL
- Maven
- Docker

---

## Сущности БД:

| -        | Course     |  
|----------|------------|
| PK       | identifier |
| String   | title      | 
| FK (M2M) | students   |  

| -        | Student     |  
|----------|-------------|
| PK       | identifier  |
| String   | name        | 
| int      | coordinator |  
| FK (M2M) | courses     |  

| -        | Coordinator |  
|----------|-------------|
| PK       | identifier  |
| String   | name        | 
| FK (O2M) | students    |

| -    | Enrolls     |  
|------|-------------|
| PK   | identifier  |
| FK   | course_id   |
| FK   | student_id  |
| Date | enroll_date |

---

## Ограничения:

- [ ] Запрещено использовать:
    - Spring
    - Hibernate;
- [ ] Должны быть реализованы не ленивые связи:
    - OneToMany
    - ManyToMany
- [ ] Сервлет должен принимать и возвращать `DTO`;
- [ ] Должны быть unit-тесты, использовать:
    - Mockito
    - Junit
- [ ] Покрытие тестами должно быть больше `80%`
- [ ] Для проверки работы репозитория (DAO) с БД использовать:
    - `testcontainers` (убедиться, что подключение в тестах происходит именно к `testcontainers`, а не к основной СУБД);
- [ ] СУБД PostgreSQL;

---

## Рекомендации

- [ ] Рекомендуется использование `Lombok` и плагина `SonarLint`;
- [ ] Не забывайте про интерфейсы, Джавадоки, логирование;
- [ ] Для инжекта пароля и логина используйте проперти;
