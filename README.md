# Дипломный проект по курсу "Тестировщик ПО"
## Перед запуском проекта и автотестов, убедитесь, что установлено следующее ПО:
* IntelliJ IDEA 2023.3.6 (Community Edition);
* Docker Desktop;
* Docker Compose;
* Java Development Kit (JDK) 11 (рекомендуется JDK 11);
* Плагин Lombok;
* Браузер, например: Google Chrome.
## Описание запуска автотестов
1. Склонируйте репозиторий на локальную машину при помощи git clone по ссылке:
2. Откройте проект в IntelliJ IDEA;
3. Запустите Docker;
4. Для запуска контейнеров введите в терминале команду docker compose up -d (MySQL, PostgresSQL, NodeJS);
// 5. После запуска контейнеров, в новом окне терминала (либо в терминале IntelliJ IDEA),запустить SUT командой java -jar artifacts/aqa-shop.jar

6. Запустите SUT в новой вкладке терминала:
* Для MySQL используйте команду: java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/app" -jar artifacts/aqa-shop.jar;
* Для PostgreSQL используйте команду: java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/app" -jar artifacts/aqa-shop.jar;
7. Проверьте доступность приложения в браузере по адресу http://localhost:8080/
8. Для запуска автотестов в новой вкладке терминала введите команду:
* Для запуска авто-тестов: ./gradlew clean test в терминале IntelliJ IDEA
// * ./gradlew clean test --info (по умолчанию запускается MySQL)
* Для запуска тестов с базой данных MySQL: ./gradlew clean test -Ddb=mysql
// ./gradlew test -Ddb.url=jdbc:postgresql://localhost:5432/app - для запуска PostgreSQL;
* Для запуска тестов с базой данных PostgresSQL: ./gradlew clean test -Ddb=postgresql
9. После прохождения всех тестов сгенерируйте отчет, введя в терминале IntelliJ IDEA команду: ./gradlew allureServe
10. После окончания всей работы введите команду для остановки SUT aqa-shop.jar - Ctrl+C;
11. Для удаления контейнеров введите в терминале команду - docker compose down.
