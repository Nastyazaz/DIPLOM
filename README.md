# Процедура запуска автотестов

После клонирования репозитория, сдеать следующие устоновки:

Для корректной работы необходимо устоновить DeBever через него подключится к СУБД PostgreSQL и
СУБД MySQL.

Так же устоновить Docker Desktop-для сборки контейнеров

В самой JAVA IDIA:

1. В терминале выполнить команду:
   `docker-compose up`
2. Открыть DeBever и подключится к СУБД
3. В новой вкладке терминала запустить приложение командой:

Для использования СУБД PostgreSQL:
`java -jar aqa-shop.jar --spring.datasource.url=jdbc:postgresql://localhost:5432/app`

Для использования СУБД MySQL:
`java -jar aqa-shop.jar --spring.datasource.url=jdbc:mysql://localhost:3306/app`

- приложение будет доступно по ссылке: http://localhost:8080/

4. В новой вкладке терминала запустить тесты командой:

Для СУБД PostgreSQL:
`./gradlew clean test "-Ddb.url=jdbc:postgresql://localhost:5432/app"`

Для СУБД MySQL:
`./gradlew clean test "-Ddb.url=jdbc:mysql://localhost:3306/app"`

5. Запустить сервис формирования отчетов Allure командой:
   `./gradlew allureServe `

-  отчет откроется автоматически в браузере.

6. Для остановки Allure в терминале ввести комбинацию клавиш Ctrl+C, нажать клавишу y.
7. Для остановки контейнеров ввести в терминале команду:
   `docker-compose down`