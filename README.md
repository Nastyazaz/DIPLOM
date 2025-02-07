# Процедура запуска автотестов


1. В терминале выполнить команду:
   `docker-compose up`
2. В новой вкладке терминала запустить приложение командой:

Для использования СУБД PostgreSQL:
`java -jar aqa-shop.jar --spring.datasource.url=jdbc:postgresql://localhost:5432/app`


- приложение будет доступно по ссылке: http://localhost:8080/

3. В новой вкладке терминала запустить прогон тестов командой:

Для СУБД PostgreSQL:
`./gradlew clean test "-Ddb.url=jdbc:postgresql://localhost:5432/app"`

